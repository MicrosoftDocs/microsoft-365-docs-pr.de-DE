---
title: Einfügen eines In-situ für ein vorläufig gelöschtes Postfach in Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie einen In-Situ-Speicher für ein vorläufig gelöschtes Postfach erstellen können, damit es inaktiv wird und der Inhalt bewahrt wird.
ms.openlocfilehash: 4dcd6539519675094da9a05c7701b9f8511ce9a1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818864"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="f660b-103">Einfügen eines In-situ für ein vorläufig gelöschtes Postfach in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f660b-103">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="f660b-104">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span><span class="sxs-lookup"><span data-stu-id="f660b-104">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span></span> <span data-ttu-id="f660b-105">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="f660b-105">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f660b-106">Da wir weiterhin auf verschiedene Arten investieren, um Postfachinhalte beizubehalten, kündigen wir den Ruhestand von in-Place-Speicher in der Exchange-Verwaltungskonsole an.</span><span class="sxs-lookup"><span data-stu-id="f660b-106">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="f660b-107">Ab dem 1. Juli 2020 können Sie in Exchange Online keine neuen in-Place-Aufbewahrungsorte erstellen.</span><span class="sxs-lookup"><span data-stu-id="f660b-107">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="f660b-108">Sie können jedoch weiterhin in-Place-Speicher in der Exchange-Verwaltungskonsole oder mithilfe des Cmdlets " **MailboxSearch** " in Exchange Online PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="f660b-108">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="f660b-109">Ab dem 1. Oktober 2020 können Sie jedoch keine in-Place-Speicher verwalten.</span><span class="sxs-lookup"><span data-stu-id="f660b-109">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="f660b-110">Sie werden nur in der Exchange-Verwaltungskonsole oder mithilfe des Cmdlets **Remove-MailboxSearch** entfernt.</span><span class="sxs-lookup"><span data-stu-id="f660b-110">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="f660b-111">Weitere Informationen zum Ruhestand von in-Place-Archiven finden Sie unter [Retirement of Legacy eDiscovery Tools](legacy-ediscovery-retirement.md).</span><span class="sxs-lookup"><span data-stu-id="f660b-111">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="f660b-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span><span class="sxs-lookup"><span data-stu-id="f660b-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="f660b-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span><span class="sxs-lookup"><span data-stu-id="f660b-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="f660b-114">What can you do?</span><span class="sxs-lookup"><span data-stu-id="f660b-114">What can you do?</span></span> <span data-ttu-id="f660b-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="f660b-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="f660b-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span><span class="sxs-lookup"><span data-stu-id="f660b-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="f660b-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span><span class="sxs-lookup"><span data-stu-id="f660b-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="f660b-118">Nachdem das Postfach deaktiviert wurde, können Sie das Postfach mithilfe der in-Place-eDiscovery in Exchange Online, der Inhaltssuche im Security & Compliance Center oder des eDiscovery Center in SharePoint Online durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="f660b-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f660b-119">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span><span class="sxs-lookup"><span data-stu-id="f660b-119">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="f660b-120">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span><span class="sxs-lookup"><span data-stu-id="f660b-120">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="f660b-121">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span><span class="sxs-lookup"><span data-stu-id="f660b-121">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span></span> <span data-ttu-id="f660b-122">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span><span class="sxs-lookup"><span data-stu-id="f660b-122">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="requirements-for-in-place-holds"></a><span data-ttu-id="f660b-123">Anforderungen für in-Place-Aufbewahrungen</span><span class="sxs-lookup"><span data-stu-id="f660b-123">Requirements for In-Place Holds</span></span>

- <span data-ttu-id="f660b-124">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span><span class="sxs-lookup"><span data-stu-id="f660b-124">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="f660b-125">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f660b-125">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 

- <span data-ttu-id="f660b-126">Wie Sie mit Windows PowerShell eine Verbindung mit Exchange Online herstellen, können Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554) nachlesen.</span><span class="sxs-lookup"><span data-stu-id="f660b-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

- <span data-ttu-id="f660b-127">Führen Sie den folgenden Befehl aus, um die Identitätsinformationen zu den vorläufig gelöschten Postfächern in Ihrer Organisation abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f660b-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="f660b-128">Weitere Informationen zu inaktiven Postfächern finden Sie unter [Overview of inactive Mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f660b-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="f660b-129">Erstellen eines In-Situ-Speichers für ein vorläufig gelöschtes Postfach, um daraus ein inaktives Postfach zu machen</span><span class="sxs-lookup"><span data-stu-id="f660b-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="f660b-130">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="f660b-130">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="f660b-131">For more information, see [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span><span class="sxs-lookup"><span data-stu-id="f660b-131">For more information, see [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="f660b-132">Erstellen Sie eine Variable, die die Eigenschaften des vorläufig gelöschten Postfachs enthält.</span><span class="sxs-lookup"><span data-stu-id="f660b-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="f660b-133">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span><span class="sxs-lookup"><span data-stu-id="f660b-133">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="f660b-134">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span><span class="sxs-lookup"><span data-stu-id="f660b-134">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="f660b-135">Create an In-Place Hold and place it on the soft-deleted mailbox.</span><span class="sxs-lookup"><span data-stu-id="f660b-135">Create an In-Place Hold and place it on the soft-deleted mailbox.</span></span> <span data-ttu-id="f660b-136">In this example, no hold duration is specified.</span><span class="sxs-lookup"><span data-stu-id="f660b-136">In this example, no hold duration is specified.</span></span> <span data-ttu-id="f660b-137">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="f660b-137">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="f660b-138">You can also specify a hold duration when you create the In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="f660b-138">You can also specify a hold duration when you create the In-Place Hold.</span></span> <span data-ttu-id="f660b-139">This example holds items in the inactive mailbox for approximately 7 years.</span><span class="sxs-lookup"><span data-stu-id="f660b-139">This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="f660b-140">Führen Sie nach ein paar Augenblicken einen der folgenden Befehle aus, um sicherzustellen, dass es sich bei dem vorläufig gelöschten Postfach um ein inaktives Postfach handelt.</span><span class="sxs-lookup"><span data-stu-id="f660b-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="f660b-141">Oder</span><span class="sxs-lookup"><span data-stu-id="f660b-141">Or</span></span>
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="f660b-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f660b-142">More information</span></span>

<span data-ttu-id="f660b-143">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span><span class="sxs-lookup"><span data-stu-id="f660b-143">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span></span> <span data-ttu-id="f660b-144">For more information, see:</span><span class="sxs-lookup"><span data-stu-id="f660b-144">For more information, see:</span></span>
  
- [<span data-ttu-id="f660b-145">Ändern der Aufbewahrungsdauer für ein inaktives Postfach</span><span class="sxs-lookup"><span data-stu-id="f660b-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="f660b-146">Wiederherstellen eines inaktiven Postfachs</span><span class="sxs-lookup"><span data-stu-id="f660b-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="f660b-147">Rückspeichern eines inaktiven Postfachs</span><span class="sxs-lookup"><span data-stu-id="f660b-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="f660b-148">[Löschen eines inaktiven Postfachs](delete-an-inactive-mailbox.md) (durch Entfernen des Haltestatus)</span><span class="sxs-lookup"><span data-stu-id="f660b-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>
