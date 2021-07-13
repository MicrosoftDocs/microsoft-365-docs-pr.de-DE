---
title: Konfigurieren der E-Mail-Weiterleitung
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Mit der E-Mail-Weiterleitung können Sie E-Mail-Nachrichten, die an ein Microsoft 365 Benutzerpostfach gesendet wurden, an ein anderes Postfach innerhalb oder außerhalb Ihrer Organisation weiterleiten.
ms.openlocfilehash: 07bd6bb1bbfd1ecdfa6ca0d545d78a39e66c7558
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393211"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="fcfbe-103">Konfigurieren der E-Mail-Weiterleitung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fcfbe-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="fcfbe-104">Als Administrator einer Organisation haben Sie möglicherweise Unternehmensanforderungen, was die Einrichtung der E-Mail-Weiterleitung für das Postfach eines Benutzers betrifft.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="fcfbe-105">Mit einer E-Mail-Weiterleitung können Sie E-Mails, die an das Postfach eines Benutzers gesendet wurden, an das Postfach eines anderen Benutzers innerhalb oder außerhalb Ihrer Organisation weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fcfbe-106">Sie können ausgehende Spamfilter-Richtlinien verwenden, um die automatische Weiterleitung an externe Empfänger zu steuern.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="fcfbe-107">Weitere Informationen finden Sie unter [Steuerung der automatischen externen E-Mail-Weiterleitung in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span><span class="sxs-lookup"><span data-stu-id="fcfbe-107">For more information, see [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="fcfbe-108">Konfigurieren der E-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="fcfbe-108">Configure email forwarding</span></span>

<span data-ttu-id="fcfbe-109">Bedenken Sie vor dem Einrichten der E-Mail-Weiterleitung Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fcfbe-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="fcfbe-110">Zulassen, dass automatisch weitergeleitete Nachrichten an Personen in der Remotedomäne gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-110">Allow automatically forwarded messages to be sent to people on the remote domain.</span></span> <span data-ttu-id="fcfbe-111">Weitere Informationen finden Sie unter [Verwalten von Remotedomänen.](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)</span><span class="sxs-lookup"><span data-stu-id="fcfbe-111">See [Manage remote domains](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) for details.</span></span>

- <span data-ttu-id="fcfbe-112">Nach dem Einrichten der E-Mail-Weiterleitung werden nur **neue** E-Mails weitergeleitet, die an das *„Von“*-Postfach gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="fcfbe-113">Für die E-Mail-Weiterleitung muss das *„Von“*-Konto über eine Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="fcfbe-114">Wenn ein Benutzer Ihre Organisation verlassen hat, ist [das Umwandeln seines Postfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md) eine alternative Option zum Einrichten der E-Mail-Weiterleitung.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="fcfbe-115">Auf diese Art und Weise können mehrere Personen darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-115">This way several people can access it.</span></span> <span data-ttu-id="fcfbe-116">Ein freigegebenes Postfach kann jedoch 50 GB nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="fcfbe-117">Um dies durchzuführen, müssen Sie ein Exchange-Administrator oder ein globaler Administrator in Microsoft 365 sein.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="fcfbe-118">Weitere Informationen finden Sie im Thema [Info zu Administratorrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="fcfbe-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fcfbe-119">Wechseln Sie im Admin Center zur Seite **Benutzer** \> **[Aktive Benutzer](https://go.microsoft.com/fwlink/p/?linkid=834822)**.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="fcfbe-120">Wählen Sie den Namen des Benutzers aus, dessen E-Mail Sie weiterleiten möchten, und öffnen Sie dann die Eigenschaftenseite.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-120">Select the name of the user whose email you want to forward, then open the properties page.</span></span>

3. <span data-ttu-id="fcfbe-121">Wählen Sie auf der Registerkarte **E-Mail** die Option **E-Mail-Weiterleitung verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="fcfbe-122">Wählen Sie auf der Seite zum Weiterleiten von E-Mails die Option **Alle an dieses Postfach gesendeten E-Mails weiterleiten** aus, geben Sie die Weiterleitungsadresse ein, und wählen Sie, ob Sie eine Kopie der weitergeleiteten E-Mails behalten möchten.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="fcfbe-123">Wenn Sie diese Option nicht sehen, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="fcfbe-124">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-124">Select **Save changes**.</span></span>

    <span data-ttu-id="fcfbe-125">**Um an mehrere E-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Outlook-Regel zum Weiterleiten an diese Adressen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> 
    
    1.  <span data-ttu-id="fcfbe-126">Öffnen  von > **Outlook-Startregeln** >  > Auswählen **von Verwaltungsregeln & Warnungen**  </span><span class="sxs-lookup"><span data-stu-id="fcfbe-126">Open **outlook** > **Home** >  **Rules** > Select **Manage Rules & Alerts**</span></span>
    1. <span data-ttu-id="fcfbe-127">Wählen Sie **"Neue Regel** > **auswählen Regel anwenden" für die Nachricht** aus, die sich am unteren Rand der Liste befindet, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="fcfbe-127">Select **New Rule** > **Select Apply rule on message I receive** located near bottom of list, then click **Next**.</span></span>
    1. <span data-ttu-id="fcfbe-128">Klicken Sie auf **"Ja",** wenn Sie gefragt werden, dass diese Regel auf jede empfangene Nachricht angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-128">Click **Yes** when asked This rule will be applied to every message you receive.</span></span> 
    1. <span data-ttu-id="fcfbe-129">Wählen Sie in der nächsten Liste die Aktionen aus, um **sie an Personen oder öffentliche Gruppen umzuleiten,** und beenden Sie die Verarbeitung weiterer **Regeln.**</span><span class="sxs-lookup"><span data-stu-id="fcfbe-129">On the next list select the actions **redirect it to people or public group** and **stop processing more rules**</span></span>
    1. <span data-ttu-id="fcfbe-130">Klicken Sie im unteren Teil des Fensters auf den unterstrichenen Ausdruck **"Personen" oder** auf die öffentliche Gruppe.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-130">Click the underlined phrase **people or public group** in the bottom part of window.</span></span>
    1. <span data-ttu-id="fcfbe-131">Geben Sie die **E-Mail-Adresse,** an die E-Mails weitergeleitet werden sollen, in das Feld "An" ein, und klicken Sie dann auf **"OK".**</span><span class="sxs-lookup"><span data-stu-id="fcfbe-131">Type the **email address** to forward mail to in the To field, then click **OK**.</span></span>
    1. <span data-ttu-id="fcfbe-132">Wählen Sie **"Fertig stellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="fcfbe-132">Select **Finish**</span></span>
    

     <span data-ttu-id="fcfbe-133">Alternativ können Sie im Admin Center [eine Verteilergruppe erstellen](../setup/create-distribution-lists.md), [die Adressen hinzufügen](add-user-or-contact-to-distribution-list.md), und dann die Weiterleitung an die Verteilergruppe einrichten, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-133">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="fcfbe-134">Löschen Sie nicht das Konto des Benutzers, dessen E-Mail Sie weiterleiten, und löschen Sie auch nicht dessen Lizenz!</span><span class="sxs-lookup"><span data-stu-id="fcfbe-134">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="fcfbe-135">Wenn Sie dies tun, wird die E-Mail-Weiterleitung beendet.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-135">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="fcfbe-136">Wechseln Sie im Admin Center zur Seite **Benutzer** \> **[Aktive Benutzer](https://go.microsoft.com/fwlink/p/?linkid=847686)**.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-136">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="fcfbe-137">Wählen Sie zum Öffnen der Eigenschaften-Seite den Namen des Benutzers aus, dessen E-Mails Sie weiterleiten wollen.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-137">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="fcfbe-138">Erweitern Sie **E-Mail-Einstellungen** und wählen Sie dann im Abschnitt **E-Mail-Weiterleitung** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-138">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="fcfbe-139">Setzen Sie auf der Seite zum Weiterleiten von E-Mails den Schalter auf **Ein**, geben Sie die Weiterleitungsadresse ein, und wählen Sie, ob Sie eine Kopie der weitergeleiteten E-Mails behalten möchten.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-139">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="fcfbe-140">Wenn Sie diese Option nicht sehen, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-140">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="fcfbe-141">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-141">Select **Save**.</span></span>

   <span data-ttu-id="fcfbe-142">**Um an mehrere E-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Outlook-Regel zum Weiterleiten an diese Adressen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-142">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="fcfbe-143">Weiter Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="fcfbe-143">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="fcfbe-144">Alternativ können Sie im Admin Center [eine Verteilergruppe erstellen](../setup/create-distribution-lists.md), [die Adressen hinzufügen](add-user-or-contact-to-distribution-list.md), und dann die Weiterleitung an die Verteilergruppe einrichten, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-144">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="fcfbe-145">Löschen Sie nicht das Konto des Benutzers, dessen E-Mail Sie weiterleiten, und löschen Sie auch nicht dessen Lizenz!</span><span class="sxs-lookup"><span data-stu-id="fcfbe-145">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="fcfbe-146">Wenn Sie dies tun, wird die E-Mail-Weiterleitung beendet.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-146">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fcfbe-147">Wechseln Sie im Admin Center zur Seite **Benutzer** \> **[Aktive Benutzer](https://go.microsoft.com/fwlink/p/?linkid=850628)**.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-147">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="fcfbe-148">Wählen Sie zum Öffnen der Eigenschaften-Seite den Namen des Benutzers aus, dessen E-Mails Sie weiterleiten wollen.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-148">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="fcfbe-149">Erweitern Sie **E-Mail-Einstellungen** und wählen Sie dann im Abschnitt **E-Mail-Weiterleitung** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-149">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="fcfbe-150">Setzen Sie auf der Seite zum Weiterleiten von E-Mails den Schalter auf **Ein**, geben Sie die Weiterleitungsadresse ein, und wählen Sie, ob Sie eine Kopie der weitergeleiteten E-Mails behalten möchten.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-150">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="fcfbe-151">Wenn Sie diese Option nicht sehen, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-151">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="fcfbe-152">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-152">Select **Save**.</span></span>

   <span data-ttu-id="fcfbe-153">**Um an mehrere E-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Outlook-Regel zum Weiterleiten an diese Adressen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-153">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="fcfbe-154">Weiter Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="fcfbe-154">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="fcfbe-155">Alternativ können Sie im Admin Center [eine Verteilergruppe erstellen](../setup/create-distribution-lists.md), [die Adressen hinzufügen](add-user-or-contact-to-distribution-list.md), und dann die Weiterleitung an die Verteilergruppe einrichten, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-155">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="fcfbe-156">Löschen Sie nicht das Konto des Benutzers, dessen E-Mail Sie weiterleiten, und löschen Sie auch nicht dessen Lizenz!</span><span class="sxs-lookup"><span data-stu-id="fcfbe-156">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span> <span data-ttu-id="fcfbe-157">Wenn Sie dies tun, wird die E-Mail-Weiterleitung beendet.</span><span class="sxs-lookup"><span data-stu-id="fcfbe-157">If you do, email forwarding will stop.</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="fcfbe-158">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="fcfbe-158">Related content</span></span> 

<span data-ttu-id="fcfbe-159">[Erstellen eines freigegebenen Postfachs](../email/create-a-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="fcfbe-159">[Create a shared mailbox](../email/create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="fcfbe-160">[Senden von E-Mails von einer anderen Adresse](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="fcfbe-160">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>\
<span data-ttu-id="fcfbe-161">[Ändern eines Benutzernamens und einer E-Mail-Adresse](../add-users/change-a-user-name-and-email-address.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="fcfbe-161">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>
