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
search.appverid:
- BCS160
- MET150
- MOE150
description: Nachdem Sie ein freigegebenes Postfach erstellt haben, sollten Sie einige Einstellungen für die Benutzer konfigurieren, z. B. E-Mail-Weiterleitung und automatische Antworten. Später möchten Sie möglicherweise andere Einstellungen ändern, z. B. den Postfachnamen oder Mitglieder.
ms.openlocfilehash: 01d5aaa686e1d64c9ea7d89913d8208f779dcfd1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52243972"
---
# <a name="configure-shared-mailbox-settings"></a><span data-ttu-id="16c18-104">Konfigurieren der Einstellungen für das freigegebene Postfach</span><span class="sxs-lookup"><span data-stu-id="16c18-104">Configure shared mailbox settings</span></span>

<span data-ttu-id="16c18-105">Nachdem Sie ein [freigegebenes](create-a-shared-mailbox.md)Postfach erstellt haben, sollten Sie einige Einstellungen für die Postfachbenutzer konfigurieren, z. B. E-Mail-Weiterleitung und automatische Antworten.</span><span class="sxs-lookup"><span data-stu-id="16c18-105">After you have [created a shared mailbox](create-a-shared-mailbox.md), you'll want to configure some settings for the mailbox users, such as email forwarding and automatic replies.</span></span> <span data-ttu-id="16c18-106">Später möchten Sie möglicherweise andere Einstellungen ändern, z. B. den Postfachnamen, Mitglieder oder Mitgliedsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="16c18-106">Later, you might want to change other settings, such as the mailbox name, members, or member permissions.</span></span> 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a><span data-ttu-id="16c18-107">Ändern des Namens oder des E-Mail-Alias eines freigegebenen Postfachs oder Ändern der primären E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="16c18-107">Change the name or email alias of a shared mailbox, or change the primary email address</span></span>

1. <span data-ttu-id="16c18-108">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="16c18-108">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="16c18-109">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten** neben **Name, E-Mail, E-Mail-Aliase aus.**</span><span class="sxs-lookup"><span data-stu-id="16c18-109">Select the shared mailbox you want to edit, and then select **Edit** next to **Name, Email, Email aliases**.</span></span>

3. <span data-ttu-id="16c18-110">Geben Sie einen neuen Namen ein, oder fügen Sie einen anderen Alias hinzu.</span><span class="sxs-lookup"><span data-stu-id="16c18-110">Enter a new name, or add another alias.</span></span> <span data-ttu-id="16c18-111">Wenn Sie die primäre E-Mail-Adresse ändern möchten, muss Ihr Postfach über mehrere E-Mail-Aliase verfügen.</span><span class="sxs-lookup"><span data-stu-id="16c18-111">If you want to change the primary email address, your mailbox must have more than one email alias.</span></span>

4. <span data-ttu-id="16c18-112">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="16c18-112">Select **Save**.</span></span>

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a><span data-ttu-id="16c18-113">Weiterleiten von E-Mails, die an ein freigegebenes Postfach gesendet wurden</span><span class="sxs-lookup"><span data-stu-id="16c18-113">Forward emails that are sent to a shared mailbox</span></span>

<span data-ttu-id="16c18-114">Sie müssen dem freigegebenen Postfach keine Lizenz zuweisen, um E-Mails weiter zu senden, die an das freigegebene Postfach gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="16c18-114">You do not need to assign a license to the shared mailbox in order to forward email that's sent to it.</span></span> <span data-ttu-id="16c18-115">Sie können die Nachrichten an eine beliebige gültige E-Mail-Adresse oder Verteilerliste weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="16c18-115">You can forward the messages to any valid email address or distribution list.</span></span>

1. <span data-ttu-id="16c18-116">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="16c18-116">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="16c18-117">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **E-Mail-Weiterleitung** \> **Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="16c18-117">Select the shared mailbox you want to edit, then select **Email forwarding** \> **Edit**.</span></span>
    
3. <span data-ttu-id="16c18-118">Legen Sie den Umschalter auf **Ein** und geben Sie eine E-Mail-Adresse ein, an die die Nachrichten weitergeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="16c18-118">Set the toggle to **On**, and enter one email address to forward the messages to.</span></span> <span data-ttu-id="16c18-119">Dies kann eine beliebige gültige E-Mail-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="16c18-119">It can be any valid email address.</span></span> <span data-ttu-id="16c18-120">Zum Weiterleiten an mehrere Adressen [](/office365/admin/setup/create-distribution-lists) müssen Sie eine Verteilergruppe für die Adressen erstellen und dann den Namen der Gruppe in dieses Feld eingeben.</span><span class="sxs-lookup"><span data-stu-id="16c18-120">To forward to multiple addresses, you need to [create a distribution group](/office365/admin/setup/create-distribution-lists) for the addresses, and then enter the name of the group in this box.</span></span>
    
4. <span data-ttu-id="16c18-121">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="16c18-121">Select **Save**.</span></span>

## <a name="send-automatic-replies-from-a-shared-mailbox"></a><span data-ttu-id="16c18-122">Senden von automatischen Antworten aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="16c18-122">Send automatic replies from a shared mailbox</span></span>

1. <span data-ttu-id="16c18-123">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="16c18-123">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="16c18-124">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie **dann Automatische Antworten** Bearbeiten \> **aus.**</span><span class="sxs-lookup"><span data-stu-id="16c18-124">Select the shared mailbox you want to edit, then select **Automatic replies** \> **Edit**.</span></span>
    
3. <span data-ttu-id="16c18-125">Setzen Sie den Schalter auf **Ein**, und wählen Sie aus, ob die Antwort an Personen innerhalb oder außerhalb Ihrer Organisation gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="16c18-125">Set the toggle to **On**, and choose whether to send the reply to people inside your organization or outside your organization.</span></span>

4. <span data-ttu-id="16c18-p106">Geben Sie die Antwort ein, die Sie an Personen innerhalb Ihrer Organisation senden möchten. Sie können nur Text (keine Bilder) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="16c18-p106">Enter the reply you want to send to people inside your organization. You can't add images, only text.</span></span>

5. <span data-ttu-id="16c18-128">Wenn Sie auch *eine* Antwort an Personen außerhalb Ihrer Organisation senden möchten, aktivieren Sie das Kontrollkästchen, wen Sie die Antwort erhalten möchten, und geben Sie den Text ein.</span><span class="sxs-lookup"><span data-stu-id="16c18-128">If you want to *also* send a reply to people outside your organization, select the check box, who you want to get the reply, and type the text.</span></span> <span data-ttu-id="16c18-129">Es ist nicht möglich, eine Antwort nur an Personen außerhalb Ihrer Organisation (ohne Einbeziehung von Personen innerhalb Ihrer Organisation) zu senden.</span><span class="sxs-lookup"><span data-stu-id="16c18-129">There's no way to only send to people outside your organization but not to people inside your organization.</span></span>

6. <span data-ttu-id="16c18-130">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="16c18-130">Select **Save**.</span></span>

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a><span data-ttu-id="16c18-131">Jedem erlauben, die gesendeten E-Mails (die Antworten) anzuzeigen</span><span class="sxs-lookup"><span data-stu-id="16c18-131">Allow everyone to see the Sent email (the replies)</span></span>

<span data-ttu-id="16c18-p108">Nachrichten, die aus dem freigegebenen Postfach gesendet wurden, werden standardmäßig nicht im Ordner "Gesendete Elemente" dieses Postfachs gespeichert. Stattdessen werden sie im Ordner "Gesendete Elemente" der Person gespeichert, die die Nachricht gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="16c18-p108">By default, messages sent from the shared mailbox aren't saved to the Sent Items folder of the shared mailbox. Instead, they are saved to the Sent Items folder of the person who sent the message.</span></span>

<span data-ttu-id="16c18-134">Wenn Sie allen Benutzern das Anzeigen der gesendeten E-Mail ermöglichen möchten, bearbeiten Sie im Admin Center die Einstellungen für freigegebene Postfächer, und wählen Sie Gesendete **Elemente** \> **Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="16c18-134">If you want to allow everyone to see the Sent email, in the admin center, edit the shared mailbox settings, and select **Sent items** \> **Edit**.</span></span>


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a><span data-ttu-id="16c18-135">Auswählen der Apps, die ein freigegebenes Postfach für den Zugriff auf Microsoft-E-Mails verwenden kann</span><span class="sxs-lookup"><span data-stu-id="16c18-135">Choose the apps that a shared mailbox can use to access Microsoft email</span></span>

1. <span data-ttu-id="16c18-136">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="16c18-136">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="16c18-137">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **E-Mail-Apps** \> **Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="16c18-137">Select the shared mailbox you want to edit, then select **Email apps** \> **Edit**.</span></span>

3. <span data-ttu-id="16c18-138">Legen Sie die Umschalte **auf Ein** für alle Apps, die Mitglieder für den Zugriff auf das freigegebene Postfach verwenden sollen.</span><span class="sxs-lookup"><span data-stu-id="16c18-138">Set the toggle to **On** for all of the apps you want members to be able to use to access the shared mailbox.</span></span> <span data-ttu-id="16c18-139">Legen Sie den Umschalter **für** apps, die sie nicht verwenden sollen, auf Aus.</span><span class="sxs-lookup"><span data-stu-id="16c18-139">Set the toggle to **Off** for any apps you don't want them to use.</span></span> 

4. <span data-ttu-id="16c18-140">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="16c18-140">Select **Save**.</span></span>


## <a name="put-a-shared-mailbox-on-litigation-hold"></a><span data-ttu-id="16c18-141">Verschieben eines freigegebenen Postfachs in das Verfahrensverfahren</span><span class="sxs-lookup"><span data-stu-id="16c18-141">Put a shared mailbox on litigation hold</span></span>

<span data-ttu-id="16c18-142">Weitere Informationen zum Prozesssicherungsverfahren finden Sie unter [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span><span class="sxs-lookup"><span data-stu-id="16c18-142">To learn more about litigation hold, see [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).</span></span>

1. <span data-ttu-id="16c18-143">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="16c18-143">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="16c18-144">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann Rechtsstreitigkeiten  \> **archivieren Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="16c18-144">Select the shared mailbox you want to edit, then select **Litigation hold** \> **Edit**.</span></span>

3. <span data-ttu-id="16c18-145">Legen Sie den Umschalter auf **Ein .**</span><span class="sxs-lookup"><span data-stu-id="16c18-145">Set the toggle to **On**.</span></span> 

4. <span data-ttu-id="16c18-146">Geben Sie optional eine Dauer, eine Notiz zum Halteraum und eine URL mit weiteren Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="16c18-146">Optionally, enter a duration, s note about the hold, and a URL with more information.</span></span>  

5. <span data-ttu-id="16c18-147">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="16c18-147">Select **Save**.</span></span>


## <a name="add-or-remove-members"></a><span data-ttu-id="16c18-148">Hinzufügen oder Entfernen von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="16c18-148">Add or remove members</span></span>

1. <span data-ttu-id="16c18-149">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="16c18-149">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="16c18-150">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie **dann Mitglieder** \> **bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="16c18-150">Select the shared mailbox you want to edit, then select **Members** \> **Edit**.</span></span>

3. <span data-ttu-id="16c18-151">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="16c18-151">Do one of the following:</span></span>
   - <span data-ttu-id="16c18-152">Wenn Sie Mitglieder hinzufügen möchten, wählen Sie **Mitglieder hinzufügen** aus, suchen oder wählen Sie ein hinzuzufügendes Mitglied aus, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="16c18-152">To add members, select **Add members**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="16c18-153">Um Mitglieder zu entfernen, verwenden Sie das Feld Suchen, um bei Bedarf nach dem Mitglied zu suchen, wählen Sie **das X** neben dem Namen des Mitglieds aus, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="16c18-153">To remove members, use the Search box to search for the member if necessary, select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="16c18-154">Wählen Sie noch mal **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="16c18-154">Select **Save** again.</span></span>

## <a name="add-or-remove-permissions-of-members"></a><span data-ttu-id="16c18-155">Hinzufügen oder Entfernen von Berechtigungen von Mitgliedern</span><span class="sxs-lookup"><span data-stu-id="16c18-155">Add or remove permissions of members</span></span>

1. <span data-ttu-id="16c18-156">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="16c18-156">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="16c18-157">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie **dann Mitglieder Berechtigungen** anpassen \> **aus.**</span><span class="sxs-lookup"><span data-stu-id="16c18-157">Select the shared mailbox you want to edit, then select **Members** \> **Customize permissions**.</span></span>

3. <span data-ttu-id="16c18-158">Wählen **Sie Bearbeiten** neben der Berechtigung aus, die Sie für ein Mitglied ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="16c18-158">Select **Edit** next to the permission you want to change for a member.</span></span> 

4. <span data-ttu-id="16c18-159">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="16c18-159">Do one of the following:</span></span>
   - <span data-ttu-id="16c18-160">Wenn Sie diesem zusätzlichen Mitglied diese Berechtigung erteilen möchten, wählen Sie Berechtigungen hinzufügen **aus,** suchen oder wählen Sie ein hinzuzufügendes Mitglied aus, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="16c18-160">To give that permission to an additional member, select **Add permissions**, search for or select a member to add, and then select **Save**.</span></span>
   - <span data-ttu-id="16c18-161">Um die Berechtigung aus einem Mitglied zu entfernen, verwenden Sie das Feld Suchen, um bei Bedarf nach dem Mitglied zu suchen, wählen Sie **das X** neben dem Namen des Mitglieds aus, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="16c18-161">To remove the permission from a member, use the Search box to search for the member if necessary,  select the **X** next to the member's name, and then select **Save**.</span></span> 

4. <span data-ttu-id="16c18-162">Wählen Sie noch mal **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="16c18-162">Select **Save** again.</span></span>

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a><span data-ttu-id="16c18-163">Ein- oder Ausblenden eines freigegebenen Postfachs in der globalen Adressliste</span><span class="sxs-lookup"><span data-stu-id="16c18-163">Show or hide a shared mailbox in the global address list</span></span>

<span data-ttu-id="16c18-164">Wenn Sie das freigegebene Postfach nicht in der globalen Adressliste anzeigen möchten, wird das Postfach nicht in der Adressliste Ihrer Organisation angezeigt, es erhält jedoch weiterhin E-Mails, die an das Postfach gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="16c18-164">If you choose not to show the shared mailbox in the global address list, the mailbox won't appear in your organization's address list, but it will still receive email sent to it.</span></span> 

1. <span data-ttu-id="16c18-165">Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.</span><span class="sxs-lookup"><span data-stu-id="16c18-165">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

2. <span data-ttu-id="16c18-166">Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie **dann Anzeigen in der globalen Adressliste** Bearbeiten \> **aus.**</span><span class="sxs-lookup"><span data-stu-id="16c18-166">Select the shared mailbox you want to edit, then select **Show in global address list** \> **Edit**.</span></span>

3. <span data-ttu-id="16c18-167">Legen Sie den Umschalter auf **Ein oder** **Aus .**</span><span class="sxs-lookup"><span data-stu-id="16c18-167">Set the toggle to **On**  or **Off**.</span></span> 

4. <span data-ttu-id="16c18-168">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="16c18-168">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="16c18-169">Das Ausblenden eines freigegebenen Postfachs aus der Adressliste macht es neuen freigegebenen Postfachmitgliedern unmöglich, das ausgeblendete Postfach ihrem Outlook-Profil hinzuzufügen, bis das freigegebene Postfach erneut in der Adressliste angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="16c18-169">Hiding a shared mailbox from address list will make it impossible for new shared mailbox members to add the hidden mailbox to their Outlook profile until the shared mailbox is again shown in the address list.</span></span> 

## <a name="related-content"></a><span data-ttu-id="16c18-170">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="16c18-170">Related content</span></span>

<span data-ttu-id="16c18-171">[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="16c18-171">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>

<span data-ttu-id="16c18-172">[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="16c18-172">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="16c18-173">[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="16c18-173">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="16c18-174">[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="16c18-174">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>

<span data-ttu-id="16c18-175">[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="16c18-175">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>