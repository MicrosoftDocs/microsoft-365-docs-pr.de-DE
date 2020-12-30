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
description: 'Hier erfahren Sie, wie Sie ein privates Postfach in ein freigegebenes Postfach konvertieren, auf das mehrere Benutzer zugreifen können. '
ms.openlocfilehash: f716bbd16be9f67189b19358ddf16a289f57f8e7
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/29/2020
ms.locfileid: "49737965"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="1ffeb-103">Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach</span><span class="sxs-lookup"><span data-stu-id="1ffeb-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="1ffeb-104">Wenn Sie das Postfach eines Benutzers in ein freigegebenes Postfach konvertieren, werden alle vorhandenen E-Mails und Kalender beibehalten.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="1ffeb-105">Sie befinden sich nun nur in einem freigegebenen Postfach, auf das mehrere Personen (nicht nur eine Person) zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="1ffeb-106">Zu einem späteren Zeitpunkt können Sie ein freigegebenes Postfach wieder in ein Benutzerpostfach (privat) konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="1ffeb-107">**Hier sind einige wirklich wichtige Dinge, die Sie kennen müssen:**</span><span class="sxs-lookup"><span data-stu-id="1ffeb-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="1ffeb-108">Das Benutzerpostfach, das Sie konvertieren möchten, benötigt eine Lizenz, die ihm zugewiesen ist, bevor Sie es in ein freigegebenes Postfach konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="1ffeb-109">Andernfalls wird die Option zum Konvertieren des Postfachs nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="1ffeb-110">Wenn Sie die Lizenz entfernt haben, fügen Sie sie erneut hinzu, damit Sie das Postfach konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="1ffeb-111">Nach dem Konvertieren des Postfachs in ein freigegebenes Postfach können Sie die Lizenz aus dem Benutzerkonto entfernen.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="1ffeb-112">Freigegebene Postfächer können bis zu 50 GB Daten haben, ohne dass Ihnen eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="1ffeb-113">Um mehr Daten zu speichern, benötigen Sie eine Lizenz, die ihr zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="1ffeb-114">Möglicherweise müssen Sie eine Reihe großer e-Mails (sprich diejenigen mit Anlagen) aus dem freigegebenen Postfach löschen, um es zu verkleinern, damit Sie die Lizenz entfernen können.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="1ffeb-p104">Löschen Sie das alte Konto des Benutzers nicht. Es ist für das Verankern des freigegebenen Postfachs erforderlich. Wenn Sie das Benutzerkonto bereits gelöscht haben, lesen Sie [Konvertieren des Postfachs eines gelöschten Benutzers](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="1ffeb-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="1ffeb-118">Die Regeln sind intakt, nachdem das Postfach in ein freigegebenes Postfach konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="1ffeb-119">Verwenden der Exchange-Verwaltungskonsole zum Konvertieren eines Postfachs</span><span class="sxs-lookup"><span data-stu-id="1ffeb-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="1ffeb-120">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="1ffeb-121">Wählen Sie **Empfänger** \> **Postfächer** aus.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="1ffeb-122">Wählen Sie das Benutzerpostfach aus.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-122">Select the user mailbox.</span></span> <span data-ttu-id="1ffeb-123">Wählen Sie unter **in freigegebenes Postfach konvertieren die** Option **konvertieren** aus.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="1ffeb-124">Wenn das Postfach kleiner als 50 GB ist, können Sie die [Lizenz vom Benutzer](../manage/remove-licenses-from-users.md)entfernen und nicht mehr bezahlen.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="1ffeb-125">Löschen Sie das Konto des Benutzers nicht.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-125">Don't delete the user's account.</span></span> <span data-ttu-id="1ffeb-126">Das freigegebene Postfach benötigt dieses als Anker.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="1ffeb-127">Wenn Sie das Postfach eines Mitarbeiters, der Ihre Organisation verlässt, konvertieren möchten, sollten Sie zusätzliche Schritte Unternehmen, um sicherzustellen, dass Sie sich nicht mehr anmelden können.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="1ffeb-128">Weitere Informationen finden Sie unter [Entfernen eines ehemaligen Mitarbeiters von Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="1ffeb-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="1ffeb-129">Es ist nicht erforderlich, das Kennwort des Benutzers während der Post Fach Konvertierung zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="1ffeb-130">Wenn das Kennwort jedoch nicht zurückgesetzt wird, **Funktionieren der ursprüngliche Benutzername und das Kennwort** nach Abschluss der Post Fach Konvertierung weiterhin.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="1ffeb-131">Alles, was Sie über freigegebene Postfächer wissen müssen, finden Sie unter [Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) und [Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="1ffeb-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1ffeb-132">Freigegebene Postfächer erfordern keine separate Lizenz.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="1ffeb-133">Wenn Sie jedoch In-Place Archiv aktivieren oder ein In-Place halten oder ein Beweissicherungsverfahren für ein freigegebenes Postfach speichern möchten, müssen Sie dem Postfach einen Exchange Onlineplan 1 mit Exchange Online Archivierungs-oder Exchange Online Plan 2-Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="1ffeb-134">Konvertieren des Postfachs eines gelöschten Benutzers</span><span class="sxs-lookup"><span data-stu-id="1ffeb-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="1ffeb-p109">Angenommen, Sie haben ein Benutzerkonto gelöscht und möchten nun das alte Postfach in ein freigegebenes Postfach konvertieren. Nachstehend wird beschrieben, wie Sie vorgehen müssen:</span><span class="sxs-lookup"><span data-stu-id="1ffeb-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="1ffeb-137">[Stellen Sie das Konto des Benutzers wieder her](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="1ffeb-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="1ffeb-138">Stellen Sie sicher, dass eine Microsoft 365-Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="1ffeb-139">Setzen Sie das Kennwort des Benutzers zurück.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="1ffeb-140">Warten Sie 20 bis 30 Minuten, bis das Postfach erneut erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="1ffeb-141">Befolgen Sie nun die Anweisungen auf dieser Seite, um das Postfach in ein freigegebenes Postfach zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="1ffeb-142">Nachdem das erledigt ist, können Sie die Lizenz aus dem Postfach des Benutzers entfernen.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="1ffeb-143">Löschen Sie das alte Postfach des Benutzers nicht.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="1ffeb-144">Das freigegebene Postfach benötigt dieses als Anker.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="1ffeb-145">Fügen Sie dem freigegebenen Postfach Mitglieder hinzu.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="1ffeb-146">Konvertieren eines freigegebenen Postfachs zurück in das (private) Postfach eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="1ffeb-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="1ffeb-147">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="1ffeb-148">Wählen Sie **Empfänger** \> **freigegeben** aus.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="1ffeb-149">Wählen Sie das freigegebene Postfach aus.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-149">Select the shared mailbox.</span></span> <span data-ttu-id="1ffeb-150">Wählen Sie unter **Convert to Regular Mailbox die** Option **Convert** aus.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="1ffeb-151">Wechseln Sie zurück zum Admin Center.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-151">Go back to the admin center.</span></span> <span data-ttu-id="1ffeb-152">Wählen Sie unter **Benutzer** das Benutzerkonto aus, das dem alten freigegebenen Postfach zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="1ffeb-153">Weisen Sie dem Konto eine Lizenz zu, und setzen Sie das Kennwort zurück.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="1ffeb-p113">Es dauert einige Minuten, bis das Postfach eingerichtet wurde. Anschließend kann die Person, die für die Verwendung dieses Kontos vorgesehen ist, das Postfach nutzen. Beim Anmelden werden die E-Mail- und Kalenderelemente angezeigt, die sich zuvor im freigegebenen Postfach befunden haben.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="1ffeb-156">Konvertieren des Postfachs eines Benutzers in einer Hybridumgebung</span><span class="sxs-lookup"><span data-stu-id="1ffeb-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="1ffeb-157">Weitere Informationen zum Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach in einer Exchange-Hybrid Umgebung finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="1ffeb-157">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="1ffeb-158">Cmdlets zum Erstellen oder Ändern eines freigegebenen remotepostfachs in einer lokalen Exchange-Umgebung</span><span class="sxs-lookup"><span data-stu-id="1ffeb-158">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="1ffeb-159">Freigegebene Postfächer werden unerwartet in Benutzerpostfächer konvertiert, nachdem die Verzeichnissynchronisierung in einer Exchange-hybridbereitstellung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-159">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](https://docs.microsoft.com/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="1ffeb-160">Wenn Sie Mitglied der Rollengruppe "Organisationsverwaltung" oder "Empfängerverwaltung" sind, können Sie die Exchange-Verwaltungsshell verwenden, um ein Benutzerpostfach in ein freigegebenes Postfach lokal zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-160">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="1ffeb-161">Beispiel: `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="1ffeb-161">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1ffeb-162">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="1ffeb-162">Related articles</span></span>

[<span data-ttu-id="1ffeb-163">Informationen zu freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="1ffeb-163">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="1ffeb-164">Erstellen eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="1ffeb-164">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="1ffeb-165">Konfigurieren eines freigegebenen Postfachs</span><span class="sxs-lookup"><span data-stu-id="1ffeb-165">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="1ffeb-166">Entfernen einer Lizenz aus einem freigegebenen Postfach</span><span class="sxs-lookup"><span data-stu-id="1ffeb-166">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="1ffeb-167">Beheben von Problemen mit freigegebenen Postfächern</span><span class="sxs-lookup"><span data-stu-id="1ffeb-167">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
