---
title: Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Erfahren Sie, wie Sie ein privates Postfach in ein freigegebenes Postfach konvertieren, auf das von mehreren Personen statt von nur einer Person zugegriffen werden kann. '
ms.openlocfilehash: 0beb85e5a69b72bcd244cd654c399e91ded06ba7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635474"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="ccd96-103">Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="ccd96-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="ccd96-104">Wenn Sie das Postfach eines Benutzers in ein freigegebenes Postfach konvertieren, werden alle vorhandenen E-Mails und Kalender beibehalten.</span><span class="sxs-lookup"><span data-stu-id="ccd96-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="ccd96-105">Sie befinden sich nun nur in einem freigegebenen Postfach, auf das mehrere Personen (nicht nur eine Person) zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="ccd96-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="ccd96-106">Zu einem späteren Zeitpunkt können Sie ein freigegebenes Postfach wieder in ein (privates) Benutzerpostfach konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ccd96-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ccd96-107">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="ccd96-107">Before you begin</span></span>

<span data-ttu-id="ccd96-108">**Hier sind einige wirklich wichtige Dinge, die Sie wissen müssen:**</span><span class="sxs-lookup"><span data-stu-id="ccd96-108">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="ccd96-109">Das benutzerpostfach, das Sie konvertieren, benötigt eine ihm zugewiesene Lizenz, bevor Sie es in ein freigegebenes Postfach konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ccd96-109">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="ccd96-110">Andernfalls wird die Option zum Konvertieren des Postfachs nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ccd96-110">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="ccd96-111">Wenn Sie die Lizenz entfernt haben, fügen Sie sie erneut hinzu, damit Sie das Postfach konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="ccd96-111">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="ccd96-112">Nach dem Konvertieren des Postfachs in ein freigegebenes Postfach können Sie die Lizenz aus dem Benutzerkonto entfernen.</span><span class="sxs-lookup"><span data-stu-id="ccd96-112">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="ccd96-113">Freigegebene Postfächer können über bis zu 50 GB Daten verfügen, ohne dass ihnen eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ccd96-113">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="ccd96-114">Um mehr Daten zu speichern, benötigen Sie eine ihm zugewiesene Lizenz.</span><span class="sxs-lookup"><span data-stu-id="ccd96-114">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="ccd96-115">Möglicherweise müssen Sie eine Reihe großer E-Mails (z. B. große E-Mails mit Anlagen) aus dem freigegebenen Postfach löschen, um es zu verkleinern, damit Sie die Lizenz entfernen können.</span><span class="sxs-lookup"><span data-stu-id="ccd96-115">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="ccd96-p104">Löschen Sie das alte Konto des Benutzers nicht. Es ist für das Verankern des freigegebenen Postfachs erforderlich. Wenn Sie das Benutzerkonto bereits gelöscht haben, lesen Sie [Konvertieren des Postfachs eines gelöschten Benutzers](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="ccd96-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="ccd96-119">Die Regeln sind intakt, nachdem das Postfach in ein freigegebenes Postfach konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ccd96-119">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="ccd96-120">Verwenden des Exchange Admin Center zum Konvertieren eines Postfachs</span><span class="sxs-lookup"><span data-stu-id="ccd96-120">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="ccd96-121">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="ccd96-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="ccd96-122">Wählen **Sie Empfänger** Postfächer \> **aus.**</span><span class="sxs-lookup"><span data-stu-id="ccd96-122">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="ccd96-123">Wählen Sie das Benutzerpostfach aus.</span><span class="sxs-lookup"><span data-stu-id="ccd96-123">Select the user mailbox.</span></span> <span data-ttu-id="ccd96-124">Wählen **Sie unter In freigegebenes Postfach konvertieren** die Option Konvertieren **aus.**</span><span class="sxs-lookup"><span data-stu-id="ccd96-124">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="ccd96-125">Wenn das Postfach kleiner als 50 GB ist, können Sie die Lizenz vom Benutzer entfernen [und](../manage/remove-licenses-from-users.md)die Zahlung für das Postfach beenden.</span><span class="sxs-lookup"><span data-stu-id="ccd96-125">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="ccd96-126">Löschen Sie das Konto des Benutzers nicht.</span><span class="sxs-lookup"><span data-stu-id="ccd96-126">Don't delete the user's account.</span></span> <span data-ttu-id="ccd96-127">Das freigegebene Postfach benötigt dieses als Anker.</span><span class="sxs-lookup"><span data-stu-id="ccd96-127">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="ccd96-128">Wenn Sie das Postfach eines Mitarbeiters konvertieren, der Ihre Organisation verlässt, sollten Sie zusätzliche Schritte ausführen, um sicherzustellen, dass sie sich nicht mehr anmelden können.</span><span class="sxs-lookup"><span data-stu-id="ccd96-128">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="ccd96-129">Weitere Informationen finden [Sie unter Entfernen eines ehemaligen Mitarbeiters aus Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="ccd96-129">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="ccd96-130">Es ist nicht erforderlich, das Kennwort des Benutzers während der Postfachkonvertierung zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="ccd96-130">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="ccd96-131">Wenn das Kennwort jedoch nicht zurückgesetzt wird, funktionieren der **ursprüngliche** Benutzername und das Kennwort weiterhin, nachdem die Postfachkonvertierung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="ccd96-131">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="ccd96-132">Weitere Informationen zu freigegebenen Postfächern finden Sie unter [Informationen](about-shared-mailboxes.md) zu freigegebenen Postfächern und [Erstellen eines freigegebenen Postfachs.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="ccd96-132">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ccd96-133">Freigegebene Postfächer erfordern keine separate Lizenz.</span><span class="sxs-lookup"><span data-stu-id="ccd96-133">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="ccd96-134">Wenn Sie jedoch In-Place Archive aktivieren oder ein In-Place-Archiv oder ein Prozesssicherungsverfahren für ein freigegebenes Postfach aktivieren möchten, müssen Sie dem Postfach eine Exchange Online Plan 1 mit Exchange Online-Archivierung- oder Exchange Online Plan 2-Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ccd96-134">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>

## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="ccd96-135">Konvertieren des Postfachs eines gelöschten Benutzers</span><span class="sxs-lookup"><span data-stu-id="ccd96-135">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="ccd96-p109">Angenommen, Sie haben ein Benutzerkonto gelöscht und möchten nun das alte Postfach in ein freigegebenes Postfach konvertieren. Nachstehend wird beschrieben, wie Sie vorgehen müssen:</span><span class="sxs-lookup"><span data-stu-id="ccd96-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="ccd96-138">[Wiederherstellen des Benutzerkontos](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="ccd96-138">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="ccd96-139">Stellen Sie sicher, Microsoft 365 ihr eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="ccd96-139">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="ccd96-140">Setzen Sie das Kennwort des Benutzers zurück.</span><span class="sxs-lookup"><span data-stu-id="ccd96-140">Reset the user's password.</span></span>
    
4. <span data-ttu-id="ccd96-141">Warten Sie 20 bis 30 Minuten, bis das Postfach erneut erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ccd96-141">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="ccd96-142">Befolgen Sie nun die Anweisungen auf dieser Seite, um das Postfach in ein freigegebenes Postfach zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="ccd96-142">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="ccd96-143">Anschließend können Sie die Lizenz aus dem Postfach des Benutzers entfernen.</span><span class="sxs-lookup"><span data-stu-id="ccd96-143">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="ccd96-144">Löschen Sie das alte Postfach des Benutzers nicht.</span><span class="sxs-lookup"><span data-stu-id="ccd96-144">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="ccd96-145">Das freigegebene Postfach benötigt dieses als Anker.</span><span class="sxs-lookup"><span data-stu-id="ccd96-145">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="ccd96-146">Fügen Sie dem freigegebenen Postfach Mitglieder hinzu.</span><span class="sxs-lookup"><span data-stu-id="ccd96-146">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="ccd96-147">Konvertieren eines freigegebenen Postfachs zurück in das (private) Postfach eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="ccd96-147">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="ccd96-148">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="ccd96-148">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="ccd96-149">Wählen **Sie Empfänger** freigegeben \> **aus.**</span><span class="sxs-lookup"><span data-stu-id="ccd96-149">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="ccd96-150">Wählen Sie das freigegebene Postfach aus.</span><span class="sxs-lookup"><span data-stu-id="ccd96-150">Select the shared mailbox.</span></span> <span data-ttu-id="ccd96-151">Wählen **Sie unter In reguläres Postfach konvertieren** die Option Konvertieren **aus.**</span><span class="sxs-lookup"><span data-stu-id="ccd96-151">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="ccd96-152">Wechseln Sie zurück zum Admin Center.</span><span class="sxs-lookup"><span data-stu-id="ccd96-152">Go back to the admin center.</span></span> <span data-ttu-id="ccd96-153">Wählen Sie unter **Benutzer** das Benutzerkonto aus, das dem alten freigegebenen Postfach zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="ccd96-153">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="ccd96-154">Weisen Sie dem Konto eine Lizenz zu, und setzen Sie das Kennwort zurück.</span><span class="sxs-lookup"><span data-stu-id="ccd96-154">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="ccd96-p113">Es dauert einige Minuten, bis das Postfach eingerichtet wurde. Anschließend kann die Person, die für die Verwendung dieses Kontos vorgesehen ist, das Postfach nutzen. Beim Anmelden werden die E-Mail- und Kalenderelemente angezeigt, die sich zuvor im freigegebenen Postfach befunden haben.</span><span class="sxs-lookup"><span data-stu-id="ccd96-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="ccd96-157">Konvertieren des Postfachs eines Benutzers in einer Hybridumgebung</span><span class="sxs-lookup"><span data-stu-id="ccd96-157">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="ccd96-158">Weitere Informationen zum Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach in Exchange Hybridumgebung finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="ccd96-158">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="ccd96-159">Cmdlets zum Erstellen oder Ändern eines freigegebenen Remotepostfachs in einer lokalen Exchange Umgebung</span><span class="sxs-lookup"><span data-stu-id="ccd96-159">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="ccd96-160">Freigegebene Postfächer werden unerwartet in Benutzerpostfächer konvertiert, nachdem die Verzeichnissynchronisierung in einer Exchange ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="ccd96-160">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="ccd96-161">Wenn Sie Mitglied der Rollengruppe Organisationsverwaltung oder Empfängerverwaltung sind, können Sie die Exchange-Verwaltungsshell verwenden, um ein Benutzerpostfach in ein lokales freigegebenes Postfach zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ccd96-161">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="ccd96-162">Beispiel: `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="ccd96-162">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-content"></a><span data-ttu-id="ccd96-163">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="ccd96-163">Related content</span></span>

<span data-ttu-id="ccd96-164">[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="ccd96-164">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="ccd96-165">[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="ccd96-165">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="ccd96-166">[Konfigurieren eines freigegebenen Postfachs](configure-a-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="ccd96-166">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="ccd96-167">[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="ccd96-167">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="ccd96-168">[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="ccd96-168">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>