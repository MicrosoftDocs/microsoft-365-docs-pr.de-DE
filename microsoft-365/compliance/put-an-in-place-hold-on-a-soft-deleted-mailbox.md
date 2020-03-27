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
description: Erfahren Sie, wie Sie einen In-Situ-Speicher für ein vorläufig gelöschtes Postfach erstellen können, damit es inaktiv wird und der Inhalt bewahrt wird. Anschließend können Sie zum Durchsuchen des inaktiven Postfachs die Microsoft eDiscovery-Tools verwenden.
ms.openlocfilehash: 1986a4bfca72c192b268984b7d2f49eb2e88134a
ms.sourcegitcommit: 7646e2d742d1b2fad085a00200a2a10461dd4bac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978155"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="ae158-104">Einfügen eines In-situ für ein vorläufig gelöschtes Postfach in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ae158-104">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="ae158-p102">Erfahren Sie, wie Sie einen In-Situ-Speicher für ein vorläufig gelöschtes Postfach erstellen können, damit es inaktiv wird und der Inhalt bewahrt wird. Anschließend können Sie zum Durchsuchen des inaktiven Postfachs die Microsoft eDiscovery-Tools verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae158-p102">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents. Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ae158-107">Da wir weiterhin auf verschiedene Arten investieren, um Postfachinhalte beizubehalten, kündigen wir den Ruhestand von in-Place-Speicher in der Exchange-Verwaltungskonsole an.</span><span class="sxs-lookup"><span data-stu-id="ae158-107">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="ae158-108">Ab dem 1. Juli 2020 können Sie in Exchange Online keine neuen in-Place-Aufbewahrungsorte erstellen.</span><span class="sxs-lookup"><span data-stu-id="ae158-108">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="ae158-109">Sie können jedoch weiterhin in-Place-Speicher in der Exchange-Verwaltungskonsole oder mithilfe des Cmdlets " **MailboxSearch** " in Exchange Online PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="ae158-109">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="ae158-110">Ab dem 1. Oktober 2020 können Sie jedoch keine in-Place-Speicher verwalten.</span><span class="sxs-lookup"><span data-stu-id="ae158-110">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="ae158-111">Sie werden nur in der Exchange-Verwaltungskonsole oder mithilfe des Cmdlets **Remove-MailboxSearch** entfernt.</span><span class="sxs-lookup"><span data-stu-id="ae158-111">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="ae158-112">Weitere Informationen zum Ruhestand von in-Place-Archiven finden Sie unter [Retirement of Legacy eDiscovery Tools](legacy-ediscovery-retirement.md).</span><span class="sxs-lookup"><span data-stu-id="ae158-112">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="ae158-113">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span><span class="sxs-lookup"><span data-stu-id="ae158-113">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="ae158-114">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span><span class="sxs-lookup"><span data-stu-id="ae158-114">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="ae158-115">What can you do?</span><span class="sxs-lookup"><span data-stu-id="ae158-115">What can you do?</span></span> <span data-ttu-id="ae158-116">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span><span class="sxs-lookup"><span data-stu-id="ae158-116">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="ae158-117">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span><span class="sxs-lookup"><span data-stu-id="ae158-117">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="ae158-118">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span><span class="sxs-lookup"><span data-stu-id="ae158-118">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="ae158-119">Nachdem das Postfach deaktiviert wurde, können Sie das Postfach mithilfe der in-Place-eDiscovery in Exchange Online, der Inhaltssuche im Security & Compliance Center oder des eDiscovery Center in SharePoint Online durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="ae158-119">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ae158-p105">In Exchange Online ist ein vorläufig gelöschtes Postfach ein Postfach, das zwar gelöscht wurde, aber innerhalb eines bestimmten Aufbewahrungszeitraums wiederhergestellt werden kann. Dieser Aufbewahrungszeitraum für vorläufig gelöschte Postfächer beträgt in Exchange Online 30 Tage. Das bedeutet, dass das Postfach innerhalb von 30 Tagen nach dem vorläufigen Löschen wiederhergestellt werden kann. Nach 30 Tagen wird ein vorläufig gelöschtes Postfach für das dauerhafte Löschen markiert und kann dann nicht mehr wiederhergestellt oder inaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="ae158-p105">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="ae158-124">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="ae158-124">Before you begin</span></span>

- <span data-ttu-id="ae158-p106">Sie müssen das **New-MailboxSearch** -Cmdlet in Windows PowerShell verwenden, um einen In-Situ-Speicher für ein vorläufig gelöschtes Postfach zu erstellen. Sie können nicht das Exchange-Verwaltungskonsole (EAC) oder das eDiscovery Center in SharePoint Online verwenden.</span><span class="sxs-lookup"><span data-stu-id="ae158-p106">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox. You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 

- <span data-ttu-id="ae158-127">Wie Sie mit Windows PowerShell eine Verbindung mit Exchange Online herstellen, können Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554) nachlesen.</span><span class="sxs-lookup"><span data-stu-id="ae158-127">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

- <span data-ttu-id="ae158-128">Führen Sie den folgenden Befehl aus, um die Identitätsinformationen zu den vorläufig gelöschten Postfächern in Ihrer Organisation abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ae158-128">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="ae158-129">Weitere Informationen zu inaktiven Postfächern finden Sie unter [Overview of inactive Mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ae158-129">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="ae158-130">Erstellen eines In-Situ-Speichers für ein vorläufig gelöschtes Postfach, um daraus ein inaktives Postfach zu machen</span><span class="sxs-lookup"><span data-stu-id="ae158-130">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="ae158-p107">Verwenden Sie das **New-MailboxSearch** -Cmdlet, um aus dem vorläufig gelöschten Postfach ein inaktives Postfach zu machen. Weitere Informationen finden Sie unter [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span><span class="sxs-lookup"><span data-stu-id="ae158-p107">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox. For more information, see [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="ae158-133">Erstellen Sie eine Variable, die die Eigenschaften des vorläufig gelöschten Postfachs enthält.</span><span class="sxs-lookup"><span data-stu-id="ae158-133">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="ae158-p108">Verwenden Sie im vorherigen Befehl den Wert der Eigenschaft **DistinguishedName** oder **ExchangeGuid** zum Identifizieren des vorläufig gelöschten Postfachs. Diese Eigenschaften sind für jedes Postfach in Ihrer Organisation eindeutig, wobei ein aktives und ein inaktives Postfach die gleiche primäre SMTP-Adresse haben können.</span><span class="sxs-lookup"><span data-stu-id="ae158-p108">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox. These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="ae158-p109">Erstellen Sie einen In-Situ-Speicher und wenden Sie ihn auf das vorläufig gelöschte Postfach an. In diesem Beispiel wird nicht angegeben, wie lange der Speicher aktiv sein soll. Das bedeutet, dass Elemente auf unbestimmte Zeit oder bis der In-Situ-Speicher für das inaktive Postfach entfernt wird, beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="ae158-p109">Create an In-Place Hold and place it on the soft-deleted mailbox. In this example, no hold duration is specified. This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="ae158-p110">Beim Erstellen des In-Situ-Speichers können Sie auch eine Aufbewahrungsdauer angeben. In diesem Beispiel werden Elemente im inaktiven Postfach für ca. 7 Jahre aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="ae158-p110">You can also specify a hold duration when you create the In-Place Hold. This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="ae158-141">Führen Sie nach ein paar Augenblicken einen der folgenden Befehle aus, um sicherzustellen, dass es sich bei dem vorläufig gelöschten Postfach um ein inaktives Postfach handelt.</span><span class="sxs-lookup"><span data-stu-id="ae158-141">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="ae158-142">Oder</span><span class="sxs-lookup"><span data-stu-id="ae158-142">Or</span></span>
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="ae158-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ae158-143">More information</span></span>

<span data-ttu-id="ae158-p111">Nachdem Sie aus einem vorläufig gelöschten Postfach ein inaktives Postfach gemacht haben, gibt es eine Reihe von Methoden, mit denen Sie das Postfach verwalten können. Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="ae158-p111">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox. For more information, see:</span></span>
  
- [<span data-ttu-id="ae158-146">Ändern der Aufbewahrungsdauer für ein inaktives Postfach</span><span class="sxs-lookup"><span data-stu-id="ae158-146">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="ae158-147">Wiederherstellen eines inaktiven Postfachs</span><span class="sxs-lookup"><span data-stu-id="ae158-147">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="ae158-148">Rückspeichern eines inaktiven Postfachs</span><span class="sxs-lookup"><span data-stu-id="ae158-148">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="ae158-149">[Löschen eines inaktiven Postfachs](delete-an-inactive-mailbox.md) (durch Entfernen des Haltestatus)</span><span class="sxs-lookup"><span data-stu-id="ae158-149">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>
