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
ms.openlocfilehash: 4cca34ab2ca3a946245f34a9b0d898a07537a722
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925521"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="f8033-103">Einfügen eines In-situ für ein vorläufig gelöschtes Postfach in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f8033-103">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="f8033-p101">Erfahren Sie, wie Sie einen In-Situ-Speicher für ein vorläufig gelöschtes Postfach erstellen können, damit es inaktiv wird und der Inhalt bewahrt wird. Anschließend können Sie zum Durchsuchen des inaktiven Postfachs die Microsoft eDiscovery-Tools verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8033-p101">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents. Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f8033-106">Da wir weiterhin auf unterschiedliche Weise investieren, um Postfachinhalte zu erhalten, wird die Rente von In-Place Holds im Exchange Admin Center (EAC) angekündigt.</span><span class="sxs-lookup"><span data-stu-id="f8033-106">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="f8033-107">Ab dem 1. Juli 2020 können Sie keine neuen In-Place in Exchange Online erstellen.</span><span class="sxs-lookup"><span data-stu-id="f8033-107">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="f8033-108">Sie können jedoch weiterhin die In-Place in der EAC oder mithilfe des **Cmdlets Set-MailboxSearch** in Exchange Online PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="f8033-108">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="f8033-109">Ab dem 1. Oktober 2020 können Sie jedoch keine In-Place verwalten.</span><span class="sxs-lookup"><span data-stu-id="f8033-109">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="f8033-110">Sie werden nur in der EAC oder mit dem **Cmdlet Remove-MailboxSearch** entfernt.</span><span class="sxs-lookup"><span data-stu-id="f8033-110">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="f8033-111">Weitere Informationen zum Austritt von In-Place finden Sie unter [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span><span class="sxs-lookup"><span data-stu-id="f8033-111">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="f8033-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span><span class="sxs-lookup"><span data-stu-id="f8033-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="f8033-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span><span class="sxs-lookup"><span data-stu-id="f8033-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="f8033-114">What can you do?</span><span class="sxs-lookup"><span data-stu-id="f8033-114">What can you do?</span></span> <span data-ttu-id="f8033-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="f8033-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="f8033-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span><span class="sxs-lookup"><span data-stu-id="f8033-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="f8033-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span><span class="sxs-lookup"><span data-stu-id="f8033-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="f8033-118">Nachdem das Postfach inaktiv gemacht wurde, können Sie das Postfach mithilfe von In-Place eDiscovery in Exchange Online, der Inhaltssuche im Security & Compliance Center oder dem eDiscovery Center in SharePoint Online durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="f8033-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f8033-p104">In Exchange Online ist ein vorläufig gelöschtes Postfach ein Postfach, das zwar gelöscht wurde, aber innerhalb eines bestimmten Aufbewahrungszeitraums wiederhergestellt werden kann. Dieser Aufbewahrungszeitraum für vorläufig gelöschte Postfächer beträgt in Exchange Online 30 Tage. Das bedeutet, dass das Postfach innerhalb von 30 Tagen nach dem vorläufigen Löschen wiederhergestellt werden kann. Nach 30 Tagen wird ein vorläufig gelöschtes Postfach für das dauerhafte Löschen markiert und kann dann nicht mehr wiederhergestellt oder inaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f8033-p104">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="requirements-for-in-place-holds"></a><span data-ttu-id="f8033-123">Anforderungen für In-Place-</span><span class="sxs-lookup"><span data-stu-id="f8033-123">Requirements for In-Place Holds</span></span>

- <span data-ttu-id="f8033-p105">Sie müssen das **New-MailboxSearch** -Cmdlet in Windows PowerShell verwenden, um einen In-Situ-Speicher für ein vorläufig gelöschtes Postfach zu erstellen. Sie können nicht das Exchange-Verwaltungskonsole (EAC) oder das eDiscovery Center in SharePoint Online verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8033-p105">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox. You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 

- <span data-ttu-id="f8033-126">Wie Sie mit Windows PowerShell eine Verbindung mit Exchange Online herstellen, können Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) nachlesen.</span><span class="sxs-lookup"><span data-stu-id="f8033-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f8033-127">Führen Sie den folgenden Befehl aus, um die Identitätsinformationen zu den vorläufig gelöschten Postfächern in Ihrer Organisation abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f8033-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="f8033-128">Weitere Informationen zu inaktiven Postfächern finden Sie [unter Übersicht über inaktive Postfächer in Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f8033-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="f8033-129">Erstellen eines In-Situ-Speichers für ein vorläufig gelöschtes Postfach, um daraus ein inaktives Postfach zu machen</span><span class="sxs-lookup"><span data-stu-id="f8033-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="f8033-p106">Verwenden Sie das **New-MailboxSearch** -Cmdlet, um aus dem vorläufig gelöschten Postfach ein inaktives Postfach zu machen. Weitere Informationen finden Sie unter [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch).</span><span class="sxs-lookup"><span data-stu-id="f8033-p106">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox. For more information, see [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch).</span></span>
  
1. <span data-ttu-id="f8033-132">Erstellen Sie eine Variable, die die Eigenschaften des vorläufig gelöschten Postfachs enthält.</span><span class="sxs-lookup"><span data-stu-id="f8033-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="f8033-p107">Verwenden Sie im vorherigen Befehl den Wert der Eigenschaft **DistinguishedName** oder **ExchangeGuid** zum Identifizieren des vorläufig gelöschten Postfachs. Diese Eigenschaften sind für jedes Postfach in Ihrer Organisation eindeutig, wobei ein aktives und ein inaktives Postfach die gleiche primäre SMTP-Adresse haben können.</span><span class="sxs-lookup"><span data-stu-id="f8033-p107">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="f8033-p108">Erstellen Sie einen In-Situ-Speicher und wenden Sie ihn auf das vorläufig gelöschte Postfach an. In diesem Beispiel wird nicht angegeben, wie lange der Speicher aktiv sein soll. Das bedeutet, dass Elemente auf unbestimmte Zeit oder bis der In-Situ-Speicher für das inaktive Postfach entfernt wird, beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="f8033-p108">Create an In-Place Hold and place it on the soft-deleted mailbox. In this example, no hold duration is specified. This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="f8033-p109">Beim Erstellen des In-Situ-Speichers können Sie auch eine Aufbewahrungsdauer angeben. In diesem Beispiel werden Elemente im inaktiven Postfach für ca. 7 Jahre aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="f8033-p109">You can also specify a hold duration when you create the In-Place Hold. This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="f8033-140">Führen Sie nach ein paar Augenblicken einen der folgenden Befehle aus, um sicherzustellen, dass es sich bei dem vorläufig gelöschten Postfach um ein inaktives Postfach handelt.</span><span class="sxs-lookup"><span data-stu-id="f8033-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="f8033-141">Oder</span><span class="sxs-lookup"><span data-stu-id="f8033-141">Or</span></span>
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="f8033-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8033-142">More information</span></span>

<span data-ttu-id="f8033-p110">Nachdem Sie aus einem vorläufig gelöschten Postfach ein inaktives Postfach gemacht haben, gibt es eine Reihe von Methoden, mit denen Sie das Postfach verwalten können. Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="f8033-p110">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox. For more information, see:</span></span>
  
- [<span data-ttu-id="f8033-145">Ändern der Aufbewahrungsdauer für ein inaktives Postfach</span><span class="sxs-lookup"><span data-stu-id="f8033-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="f8033-146">Wiederherstellen eines inaktiven Postfachs</span><span class="sxs-lookup"><span data-stu-id="f8033-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="f8033-147">Rückspeichern eines inaktiven Postfachs</span><span class="sxs-lookup"><span data-stu-id="f8033-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="f8033-148">[Löschen eines inaktiven Postfachs](delete-an-inactive-mailbox.md) (durch Entfernen des Halteraums)</span><span class="sxs-lookup"><span data-stu-id="f8033-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>