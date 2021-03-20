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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Richten Sie die E-Mail-Weiterleitung für ein oder mehrere E-Mail-Konten ein, die Office 365 verwenden.
ms.openlocfilehash: 593a4d1ca906bdee44ec00e260949ff75b582340
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915890"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="7b831-103">Konfigurieren der E-Mail-Weiterleitung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7b831-103">Configure email forwarding in Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="7b831-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="7b831-104">The admin center is changing.</span></span> <span data-ttu-id="7b831-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="7b831-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="7b831-106">Als Administrator einer Organisation haben Sie möglicherweise Unternehmensanforderungen, was die Einrichtung der E-Mail-Weiterleitung für das Postfach eines Benutzers betrifft.</span><span class="sxs-lookup"><span data-stu-id="7b831-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="7b831-107">Mit einer E-Mail-Weiterleitung können Sie E-Mails, die an das Postfach eines Benutzers gesendet wurden, an das Postfach eines anderen Benutzers innerhalb oder außerhalb Ihrer Organisation weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="7b831-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b831-108">Sie können ausgehende Spamfilter-Richtlinien verwenden, um die automatische Weiterleitung an externe Empfänger zu steuern.</span><span class="sxs-lookup"><span data-stu-id="7b831-108">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="7b831-109">Weitere Informationen finden Sie unter [Steuerung der automatischen externen E-Mail-Weiterleitung in Microsoft 365](../../security/office-365-security/external-email-forwarding.md?preserve-view=true&view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span><span class="sxs-lookup"><span data-stu-id="7b831-109">For more information, see [Control automatic external email forwarding in Microsoft 365](../../security/office-365-security/external-email-forwarding.md?preserve-view=true&view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="7b831-110">Konfigurieren der E-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="7b831-110">Configure email forwarding</span></span>

<span data-ttu-id="7b831-111">Bedenken Sie vor dem Einrichten der E-Mail-Weiterleitung Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7b831-111">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="7b831-112">Nach dem Einrichten der E-Mail-Weiterleitung werden nur **neue** E-Mails weitergeleitet, die an das *„Von“*-Postfach gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="7b831-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="7b831-113">Für die E-Mail-Weiterleitung muss das *„Von“*-Konto über eine Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="7b831-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="7b831-114">Wenn ein Benutzer Ihre Organisation verlassen hat, ist [das Umwandeln seines Postfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md) eine alternative Option zum Einrichten der E-Mail-Weiterleitung.</span><span class="sxs-lookup"><span data-stu-id="7b831-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="7b831-115">Auf diese Art und Weise können mehrere Personen darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7b831-115">This way several people can access it.</span></span> <span data-ttu-id="7b831-116">Ein freigegebenes Postfach kann jedoch 50 GB nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="7b831-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="7b831-117">Um dies durchzuführen, müssen Sie ein Exchange-Administrator oder ein globaler Administrator in Microsoft 365 sein.</span><span class="sxs-lookup"><span data-stu-id="7b831-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="7b831-118">Weitere Informationen finden Sie im Thema [Info zu Administratorrollen](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="7b831-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7b831-119">Wechseln Sie im Admin Center zur Seite **Benutzer** \> **[Aktive Benutzer](https://go.microsoft.com/fwlink/p/?linkid=834822)**.</span><span class="sxs-lookup"><span data-stu-id="7b831-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="7b831-120">Wählen Sie zum Öffnen der Eigenschaften-Seite den Namen des Benutzers aus, dessen E-Mails Sie weiterleiten wollen.</span><span class="sxs-lookup"><span data-stu-id="7b831-120">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="7b831-121">Wählen Sie auf der Registerkarte **E-Mail** die Option **E-Mail-Weiterleitung verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="7b831-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="7b831-122">Wählen Sie auf der Seite zum Weiterleiten von E-Mails die Option **Alle an dieses Postfach gesendeten E-Mails weiterleiten** aus, geben Sie die Weiterleitungsadresse ein, und wählen Sie, ob Sie eine Kopie der weitergeleiteten E-Mails behalten möchten.</span><span class="sxs-lookup"><span data-stu-id="7b831-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="7b831-123">Wenn Sie diese Option nicht sehen, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="7b831-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="7b831-124">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="7b831-124">Select **Save changes**.</span></span>

    <span data-ttu-id="7b831-125">**Um an mehrere E-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Outlook-Regel zum Weiterleiten an diese Adressen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="7b831-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="7b831-126">Weiter Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="7b831-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="7b831-127">Alternativ können Sie im Admin Center [eine Verteilergruppe erstellen](../setup/create-distribution-lists.md), [die Adressen hinzufügen](add-user-or-contact-to-distribution-list.md), und dann die Weiterleitung an die Verteilergruppe einrichten, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7b831-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="7b831-128">Löschen Sie nicht das Konto des Benutzers, dessen E-Mail Sie weiterleiten, und löschen Sie auch nicht dessen Lizenz!</span><span class="sxs-lookup"><span data-stu-id="7b831-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="7b831-129">Wenn Sie dies tun, wird die E-Mail-Weiterleitung beendet.</span><span class="sxs-lookup"><span data-stu-id="7b831-129">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7b831-130">Wechseln Sie im Admin Center zur Seite **Benutzer** \> **[Aktive Benutzer](https://go.microsoft.com/fwlink/p/?linkid=847686)**.</span><span class="sxs-lookup"><span data-stu-id="7b831-130">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="7b831-131">Wählen Sie zum Öffnen der Eigenschaften-Seite den Namen des Benutzers aus, dessen E-Mails Sie weiterleiten wollen.</span><span class="sxs-lookup"><span data-stu-id="7b831-131">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="7b831-132">Erweitern Sie **E-Mail-Einstellungen** und wählen Sie dann im Abschnitt **E-Mail-Weiterleitung** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="7b831-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="7b831-133">Setzen Sie auf der Seite zum Weiterleiten von E-Mails den Schalter auf **Ein**, geben Sie die Weiterleitungsadresse ein, und wählen Sie, ob Sie eine Kopie der weitergeleiteten E-Mails behalten möchten.</span><span class="sxs-lookup"><span data-stu-id="7b831-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="7b831-134">Wenn Sie diese Option nicht sehen, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="7b831-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="7b831-135">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="7b831-135">Select **Save**.</span></span>

   <span data-ttu-id="7b831-136">**Um an mehrere E-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Outlook-Regel zum Weiterleiten an diese Adressen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="7b831-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="7b831-137">Weiter Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="7b831-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="7b831-138">Alternativ können Sie im Admin Center [eine Verteilergruppe erstellen](../setup/create-distribution-lists.md), [die Adressen hinzufügen](add-user-or-contact-to-distribution-list.md), und dann die Weiterleitung an die Verteilergruppe einrichten, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7b831-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="7b831-139">Löschen Sie nicht das Konto des Benutzers, dessen E-Mail Sie weiterleiten, und löschen Sie auch nicht dessen Lizenz!</span><span class="sxs-lookup"><span data-stu-id="7b831-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="7b831-140">Wenn Sie dies tun, wird die E-Mail-Weiterleitung beendet.</span><span class="sxs-lookup"><span data-stu-id="7b831-140">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7b831-141">Wechseln Sie im Admin Center zur Seite **Benutzer** \> **[Aktive Benutzer](https://go.microsoft.com/fwlink/p/?linkid=850628)**.</span><span class="sxs-lookup"><span data-stu-id="7b831-141">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="7b831-142">Wählen Sie zum Öffnen der Eigenschaften-Seite den Namen des Benutzers aus, dessen E-Mails Sie weiterleiten wollen.</span><span class="sxs-lookup"><span data-stu-id="7b831-142">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="7b831-143">Erweitern Sie **E-Mail-Einstellungen** und wählen Sie dann im Abschnitt **E-Mail-Weiterleitung** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="7b831-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="7b831-144">Setzen Sie auf der Seite zum Weiterleiten von E-Mails den Schalter auf **Ein**, geben Sie die Weiterleitungsadresse ein, und wählen Sie, ob Sie eine Kopie der weitergeleiteten E-Mails behalten möchten.</span><span class="sxs-lookup"><span data-stu-id="7b831-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="7b831-145">Wenn Sie diese Option nicht sehen, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="7b831-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="7b831-146">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="7b831-146">Select **Save**.</span></span>

   <span data-ttu-id="7b831-147">**Um an mehrere E-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Outlook-Regel zum Weiterleiten an diese Adressen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="7b831-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="7b831-148">Weiter Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="7b831-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="7b831-149">Alternativ können Sie im Admin Center [eine Verteilergruppe erstellen](../setup/create-distribution-lists.md), [die Adressen hinzufügen](add-user-or-contact-to-distribution-list.md), und dann die Weiterleitung an die Verteilergruppe einrichten, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7b831-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="7b831-150">Löschen Sie nicht das Konto des Benutzers, dessen E-Mail Sie weiterleiten, und löschen Sie auch nicht dessen Lizenz!</span><span class="sxs-lookup"><span data-stu-id="7b831-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="7b831-151">Wenn Sie dies tun, wird die E-Mail-Weiterleitung beendet.</span><span class="sxs-lookup"><span data-stu-id="7b831-151">If you do, email forwarding will stop.</span></span>

::: moniker-end