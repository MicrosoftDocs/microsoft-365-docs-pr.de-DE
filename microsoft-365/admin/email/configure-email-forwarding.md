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
description: Richten Sie die E-Mail-Weiterleitung an ein oder mehrere E-Mail-Konten mithilfe von Office365 ein.
ms.openlocfilehash: 1168b549443de218339b1b8dcb32e57da175a2aa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926642"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="0d271-103">Konfigurieren der E-Mail-Weiterleitung in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0d271-103">Configure email forwarding in Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="0d271-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="0d271-104">The admin center is changing.</span></span> <span data-ttu-id="0d271-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="0d271-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="0d271-106">Als Administrator einer Organisation haben Sie möglicherweise Unternehmensanforderungen zum Einrichten der E-Mail-Weiterleitung für das Postfach eines Benutzers.</span><span class="sxs-lookup"><span data-stu-id="0d271-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="0d271-107">Mit einer E-Mail-Weiterleitung können Sie E-Mails, die an das Postfach eines Benutzers gesendet wurden, an das Postfach eines anderen Benutzers innerhalb oder außerhalb Ihrer Organisation weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="0d271-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d271-108">Sie können Filterrichtlinien für ausgehende Spamnachrichten verwenden, um die automatische Weiterleitung an externe Empfänger zu steuern.</span><span class="sxs-lookup"><span data-stu-id="0d271-108">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="0d271-109">Weitere Informationen finden Sie unter [Steuern der automatischen externen E-Mail-Weiterleitung in Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)</span><span class="sxs-lookup"><span data-stu-id="0d271-109">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="0d271-110">Konfigurieren der E-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="0d271-110">Configure email forwarding</span></span>

<span data-ttu-id="0d271-111">Beachten Sie Folgendes, bevor Sie die E-Mail-Weiterleitung einrichten:</span><span class="sxs-lookup"><span data-stu-id="0d271-111">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="0d271-112">Nachdem Sie die E-Mail-Weiterleitung eingerichtet haben, **werden** nur neue E-Mails weitergeleitet, die an das  *Von-Postfach*  gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="0d271-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="0d271-113">Für die E-Mail-Weiterleitung muss  *das Konto*  vom Server über eine Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="0d271-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="0d271-114">Wenn Sie die E-Mail-Weiterleitung einrichten, weil der Benutzer Ihre Organisation verlassen hat, besteht eine weitere Option in der Umwandlung des Postfachs in ein [freigegebenes Postfach.](convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="0d271-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="0d271-115">Auf diese Weise können mehrere Personen darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0d271-115">This way several people can access it.</span></span> <span data-ttu-id="0d271-116">Ein freigegebenes Postfach darf jedoch 50 GB nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="0d271-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="0d271-117">Sie müssen ein Exchange-Administrator oder globaler Administrator in Microsoft 365 sein, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="0d271-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="0d271-118">Weitere Informationen finden Sie im Thema zu [Administratorrollen.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="0d271-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0d271-119">Wechseln Sie im Admin Center zur **Seite** \> **["Aktive Benutzer".](https://go.microsoft.com/fwlink/p/?linkid=834822)**</span><span class="sxs-lookup"><span data-stu-id="0d271-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="0d271-120">Wählen Sie den Namen des Benutzers aus, dessen E-Mail Sie weiterleiten möchten, um die Eigenschaftenseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0d271-120">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="0d271-121">Wählen Sie **auf der Registerkarte "E-Mail"** die Option **"E-Mail-Weiterleitung verwalten" aus.**</span><span class="sxs-lookup"><span data-stu-id="0d271-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="0d271-122">Wählen Sie auf der Seite für die E-Mail-Weiterleitung alle an dieses Postfach gesendeten E-Mails weiterleiten **aus,** geben Sie die Weiterleitungsadresse ein, und wählen Sie aus, ob Sie eine Kopie der weitergeleiteten E-Mails behalten möchten.</span><span class="sxs-lookup"><span data-stu-id="0d271-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="0d271-123">Wenn diese Option nicht angezeigt wird, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="0d271-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="0d271-124">Wählen Sie **Änderungen speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="0d271-124">Select **Save changes**.</span></span>

    <span data-ttu-id="0d271-125">**Wenn Sie an mehrere E-Mail-Adressen** weiterleiten möchten, können Sie den Benutzer bitten, eine Regel in Outlook zum Weiterleiten an die Adressen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d271-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="0d271-126">Weitere Informationen finden Sie unter ["Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten".](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="0d271-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="0d271-127">Oder erstellen Sie im [](../setup/create-distribution-lists.md)Admin Center eine Verteilergruppe, fügen Sie ihr die Adressen [hinzu,](add-user-or-contact-to-distribution-list.md)und richten Sie dann die Weiterleitung so ein, dass sie mithilfe der Anweisungen in diesem Artikel auf die Verteilerliste verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="0d271-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="0d271-128">Löschen Sie nicht das Konto des Benutzers, der seine E-Mail-Adresse weiterleiten oder seine Lizenz entfernen möchte!</span><span class="sxs-lookup"><span data-stu-id="0d271-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="0d271-129">Wenn Sie dies tun, wird die E-Mail-Weiterleitung beendet.</span><span class="sxs-lookup"><span data-stu-id="0d271-129">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0d271-130">Wechseln Sie im Admin Center zur **Seite** \> **["Aktive Benutzer".](https://go.microsoft.com/fwlink/p/?linkid=847686)**</span><span class="sxs-lookup"><span data-stu-id="0d271-130">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="0d271-131">Wählen Sie den Namen des Benutzers aus, dessen E-Mail Sie weiterleiten möchten, um die Eigenschaftenseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0d271-131">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="0d271-132">Erweitern Sie die E-Mail-Einstellungen, und wählen Sie dann im Abschnitt **"E-Mail-Weiterleitung"** die Option  **"Bearbeiten" aus.**</span><span class="sxs-lookup"><span data-stu-id="0d271-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="0d271-133">Legen Sie auf der E-Mail-Weiterleitungsseite die Umschalttaste auf **"Ein"** fest, geben Sie die Weiterleitungsadresse ein, und wählen Sie aus, ob Sie eine Kopie der weitergeleiteten E-Mails behalten möchten.</span><span class="sxs-lookup"><span data-stu-id="0d271-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="0d271-134">Wenn diese Option nicht angezeigt wird, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="0d271-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="0d271-135">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0d271-135">Select **Save**.</span></span>

   <span data-ttu-id="0d271-136">**Wenn Sie an mehrere E-Mail-Adressen** weiterleiten möchten, können Sie den Benutzer bitten, eine Regel in Outlook zum Weiterleiten an die Adressen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d271-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="0d271-137">Weitere Informationen finden Sie unter ["Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten".](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="0d271-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="0d271-138">Oder erstellen Sie im [](../setup/create-distribution-lists.md)Admin Center eine Verteilergruppe, fügen Sie ihr die Adressen [hinzu,](add-user-or-contact-to-distribution-list.md)und richten Sie dann die Weiterleitung so ein, dass sie mithilfe der Anweisungen in diesem Artikel auf die Verteilerliste verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="0d271-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="0d271-139">Löschen Sie nicht das Konto des Benutzers, der seine E-Mail-Adresse weiterleiten oder seine Lizenz entfernen möchte!</span><span class="sxs-lookup"><span data-stu-id="0d271-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="0d271-140">Wenn Sie dies tun, wird die E-Mail-Weiterleitung beendet.</span><span class="sxs-lookup"><span data-stu-id="0d271-140">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0d271-141">Wechseln Sie im Admin Center zur **Seite** \> **["Aktive Benutzer".](https://go.microsoft.com/fwlink/p/?linkid=850628)**</span><span class="sxs-lookup"><span data-stu-id="0d271-141">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="0d271-142">Wählen Sie den Namen des Benutzers aus, dessen E-Mail Sie weiterleiten möchten, um die Eigenschaftenseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0d271-142">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="0d271-143">Erweitern Sie die E-Mail-Einstellungen, und wählen Sie dann im Abschnitt **"E-Mail-Weiterleitung"** die Option  **"Bearbeiten" aus.**</span><span class="sxs-lookup"><span data-stu-id="0d271-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="0d271-144">Legen Sie auf der E-Mail-Weiterleitungsseite die Umschalttaste auf **"Ein"** fest, geben Sie die Weiterleitungsadresse ein, und wählen Sie aus, ob Sie eine Kopie der weitergeleiteten E-Mails behalten möchten.</span><span class="sxs-lookup"><span data-stu-id="0d271-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="0d271-145">Wenn diese Option nicht angezeigt wird, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="0d271-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="0d271-146">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0d271-146">Select **Save**.</span></span>

   <span data-ttu-id="0d271-147">**Wenn Sie an mehrere E-Mail-Adressen** weiterleiten möchten, können Sie den Benutzer bitten, eine Regel in Outlook zum Weiterleiten an die Adressen einrichten.</span><span class="sxs-lookup"><span data-stu-id="0d271-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="0d271-148">Weitere Informationen finden Sie unter ["Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten".](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)</span><span class="sxs-lookup"><span data-stu-id="0d271-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="0d271-149">Oder erstellen Sie im [](../setup/create-distribution-lists.md)Admin Center eine Verteilergruppe, fügen Sie ihr die Adressen [hinzu,](add-user-or-contact-to-distribution-list.md)und richten Sie dann mithilfe der Anweisungen in diesem Artikel die Weiterleitung so ein, dass sie auf die Verteilerliste verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="0d271-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="0d271-150">Löschen Sie nicht das Konto des Benutzers, der die E-Mail-Adresse, die Sie weiterleiten, weiterleiten oder seine Lizenz entfernen.</span><span class="sxs-lookup"><span data-stu-id="0d271-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="0d271-151">Wenn Sie dies tun, wird die E-Mail-Weiterleitung beendet.</span><span class="sxs-lookup"><span data-stu-id="0d271-151">If you do, email forwarding will stop.</span></span>

::: moniker-end
