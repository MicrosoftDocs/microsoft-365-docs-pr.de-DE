---
title: Benutzer hinzufügen und Lizenzen zuweisen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
description: Erfahren Sie, wie Sie gleichzeitig mehrere Benutzer hinzufügen und Lizenzen für Microsoft 365 zuweisen können.
ms.date: 07/01/2020
ms.openlocfilehash: 3efa32d21a21ed12041f5731296c1b033374712f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274388"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a><span data-ttu-id="54f9b-103">Gleichzeitiges Hinzufügen von Benutzern und Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="54f9b-103">Add users and assign licenses at the same time</span></span>

<span data-ttu-id="54f9b-p101">Jedes Mitglied Ihres Teams benötigt ein Benutzerkonto, um sich bei [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business) anmelden und darauf zugreifen zu können. Die einfachste Methode zum Hinzufügen von Benutzerkonten besteht darin, diese im Microsoft 365 Admin Center einzeln hinzuzufügen. Nach Abschluss dieses Schritts verfügen Ihre Teammitglieder über Microsoft 365-Lizenzen, Anmeldeinformationen und Microsoft 365-Postfächer.</span><span class="sxs-lookup"><span data-stu-id="54f9b-p101">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://www.microsoft.com/microsoft-365/business). The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center. After you do this step, your users have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="54f9b-107">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="54f9b-107">Before you begin</span></span>

<span data-ttu-id="54f9b-108">Sie müssen ein globaler, Lizenz- oder Benutzeradministrator sein, um Benutzer hinzufügen und Lizenzen zuweisen zu können.</span><span class="sxs-lookup"><span data-stu-id="54f9b-108">You must be a global, license, or a user admin to add users and assign licenses.</span></span> <span data-ttu-id="54f9b-109">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="54f9b-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="add-a-user-in-the-admin-simplified-view"></a><span data-ttu-id="54f9b-110">Hinzufügen eines Benutzers in der vereinfachten Administrator-Ansicht</span><span class="sxs-lookup"><span data-stu-id="54f9b-110">Add a user in the admin simplified view</span></span>

<span data-ttu-id="54f9b-111">Wenn Sie diese Seite im Admin Center sehen, dann befinden Sie sich auf der **vereinfachten Administrator-Ansicht**.</span><span class="sxs-lookup"><span data-stu-id="54f9b-111">If you're seeing this page in the admin center, you're on the **admin simplified view**.</span></span> <span data-ttu-id="54f9b-112">Führen Sie die folgenden Schritte aus, um einen Benutzer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="54f9b-112">Follow the steps below to add a user.</span></span>

:::image type="content" source="../../media/vsb-add-user-view.png" alt-text="Screenshot: Vereinfachte Admin Center-Ansicht":::

::: moniker range="o365-worldwide"

1. <span data-ttu-id="54f9b-114">Wechseln Sie zum Admin Center unter <https://admin.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="54f9b-114">Go to the admin center at <https://admin.microsoft.com>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="54f9b-115">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span><span class="sxs-lookup"><span data-stu-id="54f9b-115">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="54f9b-116">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="54f9b-116">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="54f9b-117">Wählen Sie **Ein Konto für eine andere Person erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="54f9b-117">Select **Create an account for another person**.</span></span>
3. <span data-ttu-id="54f9b-118">Geben Sie auf der Seite **Benutzerkonto hinzufügen** die Vor- und Nachnamen ein, den Anzeigenamen und den Benutzernamen, den die Person für die Anmeldung verwenden wird.</span><span class="sxs-lookup"><span data-stu-id="54f9b-118">On the **Add a user account** page, fill in the first and last name, display name, and username they'll use to sign in.</span></span>
4. <span data-ttu-id="54f9b-119">Fügen Sie die E-Mail-Adresse des Benutzers im Textfeld **Bis zu 5 E-Mail-Adressen...** hinzu.</span><span class="sxs-lookup"><span data-stu-id="54f9b-119">Add the email address of the user in the **Up to 5 email addresses...** text box.</span></span> <span data-ttu-id="54f9b-120">Dies wird sicherstellen, dass der neue Benutzer die Informationen erhält, die er für die Anmeldung bei den Microsoft 365-Diensten benötigt.</span><span class="sxs-lookup"><span data-stu-id="54f9b-120">This will make sure the new user gets the information they need to sign into Microsoft 365 services.</span></span>
5. <span data-ttu-id="54f9b-121">Wählen Sie **Benutzer hinzufügen** und **Anmeldeinformation herunterladen** aus, wenn Sie diese Info speichern wollen.</span><span class="sxs-lookup"><span data-stu-id="54f9b-121">Select **Add user** and **Download sign-in info** if you want to save this info.</span></span>

## <a name="watch-add-users-in-the-dashboard-view"></a><span data-ttu-id="54f9b-122">Video: Hinzufügen von Benutzern in der Dashboard-Ansicht</span><span class="sxs-lookup"><span data-stu-id="54f9b-122">Watch: Add users in the dashboard view</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> <span data-ttu-id="54f9b-123">Die im Video verwendeten Schritte beginnen mit dem Hinzufügen von Benutzern bei einem anderen Ausgangspunkt, aber die übrigen Schritte sind mit dem folgenden Verfahren identisch.</span><span class="sxs-lookup"><span data-stu-id="54f9b-123">The steps used in the video show a different starting point for adding users, but the remaining steps are the same as the following procedure.</span></span>

## <a name="add-users-one-at-a-time-in-the-dashboard-view"></a><span data-ttu-id="54f9b-124">Benutzer einzeln in der Dashboard-Ansicht hinzufügen</span><span class="sxs-lookup"><span data-stu-id="54f9b-124">Add users one at a time in the dashboard view</span></span>

:::image type="content" source="../../media/classic-admin-center.png" alt-text="Screenshot: Dashboard-Ansicht des Admin Centers":::

::: moniker range="o365-worldwide"

1. <span data-ttu-id="54f9b-126">Wechseln Sie zum Admin Center unter <https://admin.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="54f9b-126">Go to the admin center at <https://admin.microsoft.com>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="54f9b-127">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span><span class="sxs-lookup"><span data-stu-id="54f9b-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="54f9b-128">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="54f9b-128">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="54f9b-129">Wählen Sie **Benutzer** > **Aktive Benutzer** und **Benutzer hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="54f9b-129">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
3. <span data-ttu-id="54f9b-130">Geben Sie im Bereich **Grundlagen einrichten** die grundlegenden Benutzerinformationen ein, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="54f9b-130">In the **Set up the basics** pane, fill in the basic user information, and then select **Next**.</span></span>
    - <span data-ttu-id="54f9b-131">**Name** Geben Sie den Vor- und Nachnamen, den Anzeigenamen und den Benutzernamen ein.</span><span class="sxs-lookup"><span data-stu-id="54f9b-131">**Name** Fill in the first and last name, display name, and username.</span></span>
    - <span data-ttu-id="54f9b-p105">**Domäne** Wählen Sie die Domäne für das Konto des Benutzers aus. Wenn beispielsweise der Benutzername des Benutzers „Jakob“ ist und die Domäne „contoso.com“ heißt, meldet er sich durch Eingabe von „jakob@contoso.com“ an.</span><span class="sxs-lookup"><span data-stu-id="54f9b-p105">**Domain** Choose the domain for the user's account. For example, if the user's username is Jakob, and the domain is contoso.com, they'll sign in by using jakob@contoso.com.</span></span>
    - <span data-ttu-id="54f9b-134">**Kennworteinstellungen** Wählen Sie, ob Sie das automatisch generierte Kennwort verwenden oder Ihr eigenes sicheres Kennwort für den Benutzer erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="54f9b-134">**Password settings** Choose to use the autogenerated password or to create your own strong password for the user.</span></span>
    - <span data-ttu-id="54f9b-p106">Der Benutzer muss sein Kennwort nach 90 Tagen ändern. Sie können aber auch Folgendes auswählen: **Vom Benutzer verlangen, dass er sein Kennwort bei der ersten Anmeldung ändern muss**.</span><span class="sxs-lookup"><span data-stu-id="54f9b-p106">The user must change their password after 90 days. Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    - <span data-ttu-id="54f9b-137">Wählen Sie aus, ob das Kennwort per E-Mail gesendet werden soll, wenn der Benutzer hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="54f9b-137">Choose whether you want to  send the password in email when the user is added.</span></span>
4. <span data-ttu-id="54f9b-138">Wählen Sie im Bereich **Produktlizenzen zuweisen** den Speicherort und die entsprechende Lizenz für den Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="54f9b-138">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="54f9b-139">Wenn Sie keine Lizenzen zur Verfügung haben, können Sie trotzdem einen Benutzer hinzufügen und zusätzliche Lizenzen kaufen.</span><span class="sxs-lookup"><span data-stu-id="54f9b-139">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="54f9b-140">Erweitern Sie **Apps**, und aktivieren oder deaktivieren Sie Apps, um die Apps einzuschränken, für die der Benutzer eine Lizenz hat.</span><span class="sxs-lookup"><span data-stu-id="54f9b-140">Expand **Apps** and select or deselect apps to limit the apps the user has a license for.</span></span> <span data-ttu-id="54f9b-141">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="54f9b-141">Select **Next**.</span></span>
5. <span data-ttu-id="54f9b-142">Erweitern Sie auf der Seite **Optionale Einstellungen** die Option **Rollen**, um diesen Benutzer als Administrator festzulegen. Erweitern Sie **Profilinformationen**, um weitere Informationen zum Benutzer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="54f9b-142">In the **Optional settings** pane, expand **Roles** to make this user an admin. Expand **Profile info** to add additional information about the user.</span></span>
6. <span data-ttu-id="54f9b-143">Wählen Sie **Weiter** aus, überprüfen Sie die Einstellungen des neuen Benutzers, nehmen Sie eventuell Änderungen vor, und wählen Sie dann **Hinzufügen fertig stellen** > **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="54f9b-143">Select **Next**, review your new user's settings, make any changes you like, then select **Finish adding**, then **Close**.</span></span>

## <a name="add-multiple-users-at-the-same-time"></a><span data-ttu-id="54f9b-144">Gleichzeitiges Hinzufügen von mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="54f9b-144">Add multiple users at the same time</span></span>

<span data-ttu-id="54f9b-145">Sie können eine der folgenden Methoden verwenden, um mehrere Benutzer gleichzeitig hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="54f9b-145">You can use any of the following methods to add multiple users at the same time:</span></span>

- <span data-ttu-id="54f9b-146">**Mithilfe einer Kalkulationstabelle können Sie Benutzer in Massen hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="54f9b-146">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="54f9b-147">Weitere Informationen hierzu finden Sie unter [Gleichzeitiges Hinzufügen von mehreren Benutzern](../../enterprise/add-several-users-at-the-same-time.md).</span><span class="sxs-lookup"><span data-stu-id="54f9b-147">See [Add several users at the same time](../../enterprise/add-several-users-at-the-same-time.md).</span></span>
- <span data-ttu-id="54f9b-p109">**Automatisieren Sie das Hinzufügen von Konten und Zuweisen von Lizenzen.** Lesen Sie dazu [Erstellen von Benutzerkonten mit Microsoft 365 PowerShell](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md). Wählen Sie diese Methode, wenn Sie mit der Nutzung von Windows PowerShell-Cmdlets bereits vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="54f9b-p109">**Automate adding accounts and assigning licenses.** See [Create user accounts with Microsoft 365 PowerShell](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md). Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
- <span data-ttu-id="54f9b-p110">**Sie verwenden Active Directory?**[Richten Sie die Directory-Synchronisierung für Microsoft 365 ein](../../enterprise/set-up-directory-synchronization.md). Mithilfe des Azure AD Connect-Tools können Sie Active Directory-Benutzerkonten (und andere Active Directory-Objekte) in Microsoft 365 replizieren. Bei der Synchronisierung werden nur die Benutzerkonten hinzugefügt. Sie müssen den synchronisierten Benutzern Lizenzen zuweisen, damit diese E-Mail und andere Office-Apps verwenden können.</span><span class="sxs-lookup"><span data-stu-id="54f9b-p110">**Using ActiveDirectory?** [Set up directory synchronization for Microsoft 365](../../enterprise/set-up-directory-synchronization.md). Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Microsoft 365. The sync only adds the user accounts. You must assign licenses to the synced users before they can use email and other Office apps.</span></span>
- <span data-ttu-id="54f9b-156">**Sie migrieren aus Exchange?**</span><span class="sxs-lookup"><span data-stu-id="54f9b-156">**Migrating from Exchange?**</span></span> <span data-ttu-id="54f9b-157">Siehe [Methoden zum Migrieren mehrerer E-Mail-Konten zu Office 365](/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="54f9b-157">See [Ways to migrate multiple email accounts to Office 365](/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="54f9b-158">Wenn Sie mithilfe einer Übernahmemigration oder mit einer mehrstufigen bzw. hybriden Exchange-Methode mehrere Postfächer zu Microsoft 365 migrieren, werden die Benutzer als Teil der Migration automatisch hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="54f9b-158">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you automatically add users as part of the migration.</span></span> <span data-ttu-id="54f9b-159">Bei der Migration werden nur die Benutzerkonten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="54f9b-159">The migration only adds the user accounts.</span></span> <span data-ttu-id="54f9b-160">Sie müssen den Benutzern Lizenzen zuweisen, damit sie E-Mail und andere Office-Apps verwenden können.</span><span class="sxs-lookup"><span data-stu-id="54f9b-160">You must assign licenses to the users before they can use email and other Office apps.</span></span> <span data-ttu-id="54f9b-161">Wenn Sie einem Benutzer keine Lizenz zuweisen, wird sein Postfach nach Ablauf einer 30-tägigen Kulanzzeit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="54f9b-161">If you don't assign a license to a user, their mailbox is disabled after a grace period of 30 days.</span></span> <span data-ttu-id="54f9b-162">Erfahren Sie, wie Sie unter Verwendung des Microsoft 365 Admin Centers [Benutzern Lizenzen zuweisen](../manage/assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="54f9b-162">Learn how to [assign licenses to users](../manage/assign-licenses-to-users.md) in the Microsoft 365 admin center.</span></span>

## <a name="next-steps"></a><span data-ttu-id="54f9b-163">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="54f9b-163">Next steps</span></span>

<span data-ttu-id="54f9b-164">Nachdem Sie einen Benutzer hinzugefügt haben, erhalten Sie eine E-Mail-Benachrichtigung von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="54f9b-164">After you add a user, you get an email notification from Microsoft.</span></span> <span data-ttu-id="54f9b-165">Die E-Mail enthält die Benutzer-ID und das Kennwort der Person, damit sie sich bei Microsoft 365 anmelden kann.</span><span class="sxs-lookup"><span data-stu-id="54f9b-165">The email contains the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="54f9b-166">Verwenden Sie hierzu Ihre normale Vorgehensweise für die Übermittlung neuer Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="54f9b-166">Use your normal process for communicating new passwords.</span></span> <span data-ttu-id="54f9b-167">Geben Sie die [Mitarbeiter-Kurzanleitung](../../business-video/employee-quick-setup.md) für Ihre neuen Benutzer frei, um die Umgebung einzurichten, z. B. [wie Office-Apps heruntergeladen und auf einem PC oder Mac installiert werden](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658), und [wie Office-Apps und E-Mails auf einem mobilen Gerät eingerichtet werden](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="54f9b-167">Share the [Employee quickstart guide](../../business-video/employee-quick-setup.md) with your new users to set up things, like how to [download and install Office apps on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and how to [set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="54f9b-168">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="54f9b-168">Related content</span></span>

<span data-ttu-id="54f9b-169">[Hinzufügen eines neuen Mitarbeiters zu Microsoft 365](add-new-employee.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="54f9b-169">[Add a new employee to Microsoft 365](add-new-employee.md) (article)</span></span>\
<span data-ttu-id="54f9b-170">[Gleichzeitiges Hinzufügen mehrerer Benutzer zu Microsoft 365](../../enterprise/add-several-users-at-the-same-time.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="54f9b-170">[Add several users at the same time to Microsoft 365](../../enterprise/add-several-users-at-the-same-time.md) (article)</span></span>\
<span data-ttu-id="54f9b-171">[Wiederherstellen eines Benutzers in Microsoft 365](restore-user.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="54f9b-171">[Restore a user in Microsoft 365](restore-user.md) (article)</span></span>\
<span data-ttu-id="54f9b-172">[Zuweisen von Lizenzen zu Benutzern ](../manage/assign-licenses-to-users.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="54f9b-172">[Assign licenses to users](../manage/assign-licenses-to-users.md) (article)</span></span>\
<span data-ttu-id="54f9b-173">[Löschen eines Benutzers aus Ihrer Organisation](delete-a-user.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="54f9b-173">[Delete a user from your organization](delete-a-user.md) (article)</span></span>
