---
title: Löschen eines inaktiven Postfachs in Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: Wenn Sie den Inhalt eines Office 365 inaktiven Postfachs nicht mehr aufbewahren müssen, können Sie das inaktive Postfach endgültig löschen, indem Sie den Haltebereich entfernen. Nach dem Entfernen des haltebereichs wird das inaktive Postfach zum Löschen markiert und endgültig gelöscht, nachdem es verarbeitet wurde.
ms.openlocfilehash: 21df7f34d6f07a413b860b1b918eb1dbdf26e946
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595330"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="b0256-104">Löschen eines inaktiven Postfachs in Office 365</span><span class="sxs-lookup"><span data-stu-id="b0256-104">Delete an inactive mailbox in Office 365</span></span>

<span data-ttu-id="b0256-105">Ein inaktives Postfach wird verwendet, um die E-Mails eines ehemaligen Mitarbeiters aufzubewahren, nachdem dieser die Organisation verlassen hat.</span><span class="sxs-lookup"><span data-stu-id="b0256-105">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="b0256-106">Wenn Sie die Inhalte eines inaktiven Postfachs nicht mehr aufbewahren müssen, können Sie das inaktive Postfach durch Entfernen des Haltebereichs endgültig löschen.</span><span class="sxs-lookup"><span data-stu-id="b0256-106">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="b0256-107">Darüber hinaus ist es möglich, mehrere Haltebereiche für ein inaktives Postfach festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b0256-107">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="b0256-108">Beispielsweise kann für ein inaktives Postfach ein Beweissicherungsverfahren aktiviert oder das Postfach in einem oder mehreren In-Situ-Speichern abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b0256-108">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="b0256-109">Darüber hinaus kann eine Office 365 Aufbewahrungsrichtlinie (erstellt im Security and Compliance Center in Office 365 oder Microsoft 365) auf das inaktive Postfach angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0256-109">Additionally, an Office 365 retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="b0256-110">Sie müssen alle Haltebereiche und Office 365-Aufbewahrungsrichtlinien von einem inaktiven Postfach entfernen, um dieses löschen zu können.</span><span class="sxs-lookup"><span data-stu-id="b0256-110">You have to remove all holds and Office 365 retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="b0256-111">Nach dem Entfernen der Haltebereiche und Aufbewahrungsrichtlinien wird das inaktive Postfach zum Löschen markiert und endgültig gelöscht, nachdem es verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="b0256-111">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b0256-112">Da wir weiterhin auf verschiedene Arten investieren, um Postfachinhalte beizubehalten, kündigen wir den Ruhestand von in-Place-Speicher in der Exchange-Verwaltungskonsole an.</span><span class="sxs-lookup"><span data-stu-id="b0256-112">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="b0256-113">Das bedeutet, dass Sie das Beweissicherungsverfahren und Office 365 Aufbewahrungsrichtlinien verwenden sollten, um ein inaktives Postfach zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b0256-113">That means you should use Litigation Holds and Office 365 retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="b0256-114">Ab dem 1. April 2020 können Sie in Exchange Online keine neuen in-Place-Aufbewahrungsorte erstellen.</span><span class="sxs-lookup"><span data-stu-id="b0256-114">Starting April 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="b0256-115">Sie können jedoch weiterhin die Aufbewahrungsdauer eines in-situ-Speichers ändern, der in einem inaktiven Postfach platziert wird.</span><span class="sxs-lookup"><span data-stu-id="b0256-115">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="b0256-116">Ab dem 1. Juli 2020 können Sie die Aufbewahrungsdauer jedoch nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="b0256-116">However, starting July 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="b0256-117">Sie können ein inaktives Postfach nur löschen, indem Sie den in-situ-Speicher entfernen.</span><span class="sxs-lookup"><span data-stu-id="b0256-117">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="b0256-118">Vorhandene inaktive Postfächer, die sich im Compliance-Archiv befinden, werden weiterhin beibehalten, bis die Aufbewahrung aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="b0256-118">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="b0256-119">Weitere Informationen zum Ruhestand von in-Place-Archiven finden Sie unter [Retirement of Legacy eDiscovery Tools](legacy-ediscovery-retirement.md).</span><span class="sxs-lookup"><span data-stu-id="b0256-119">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="b0256-120">Eine Beschreibung dessen, was geschieht, wenn Haltebereiche von einem inaktiven Postfach entfernt werden, finden Sie im Abschnitt [Weitere Informationen](#more-information).</span><span class="sxs-lookup"><span data-stu-id="b0256-120">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="b0256-121">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="b0256-121">Before you begin</span></span>

- <span data-ttu-id="b0256-122">Sie müssen Exchange Online PowerShell zum Entfernen eines Beweissicherungsverfahrens für ein inaktives Postfach verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0256-122">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="b0256-123">Sie können nicht die Exchange-Verwaltungskonsole (EAC) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0256-123">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="b0256-124">Eine Schritt-für-Schritt-Anleitung finden Sie unter [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="b0256-124">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="b0256-125">Sie können die Exchange Online PowerShell oder die EAC verwenden, um einen In-Situ-Speicher von einem inaktiven Postfach zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b0256-125">You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="b0256-126">Sie können die Inhalte eines inaktiven Postfachs in ein anderes Postfach kopieren, bevor Sie den Haltebereich entfernen und ein inaktives Postfach löschen.</span><span class="sxs-lookup"><span data-stu-id="b0256-126">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="b0256-127">Ausführliche Informationen finden Sie unter [Wiederherstellen eines inaktiven Postfachs in Office 365](restore-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="b0256-127">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="b0256-128">Wenn Sie den Haltebereich oder die Office 365-Aufbewahrungsrichtlinie für ein inaktives Postfach entfernen, während die Beibehaltungsdauer für das vorläufig gelöschte Postfach abgelaufen ist, wird das Postfach dauerhaft gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b0256-128">If you remove the hold or Office 365 retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="b0256-129">Nachdem es gelöscht wurde, kann es nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b0256-129">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="b0256-130">Stellen Sie vor dem Entfernen des Haltebereichs sicher, dass Sie die Inhalte im Postfach nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="b0256-130">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="b0256-131">Wenn Sie ein inaktives Postfach erneut aktivieren möchten, können Sie es wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="b0256-131">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="b0256-132">Ausführliche Informationen finden Sie unter [Wiederherstellen eines inaktiven Postfachs in Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="b0256-132">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="b0256-133">Weitere Informationen zu inaktiven Postfächern finden Sie unter [inactive Mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="b0256-133">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="b0256-134">Schritt 1: Identifizieren der Haltebereiche für ein inaktives Postfach</span><span class="sxs-lookup"><span data-stu-id="b0256-134">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="b0256-p107">Wie bereits erwähnt, kann ein Beweissicherungsverfahren, ein In-Situ-Speicher oder eine Office 365-Aufbewahrungsrichtlinie für ein inaktives Postfach aktiviert werden. Der erste Schritt besteht darin, die Haltebereiche für ein inaktives Postfach zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b0256-p107">As previously stated, a Litigation Hold, In-Place Hold, or Office 365 retention policy might be placed on an inactive mailbox. The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="b0256-137">Führen Sie den folgenden Befehl aus, um die Informationen zu Haltebereichen für alle inaktiven Postfächer in Ihrer Organisation anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b0256-137">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="b0256-p108">Der Wert **True** für die Eigenschaft **LitigationHoldEnabled** gibt an, dass für das inaktive Postfach ein Beweissicherungsverfahren aktiviert ist. Wenn ein In-Situ-Speicher für ein inaktives Postfach aktiviert ist, wird die GUID für den Haltebereich als Wert für die Eigenschaft **InPlaceHolds** angezeigt. Die folgenden Ergebnisse für zwei inaktive Postfächer zeigen beispielsweise, dass für Ann Beebe ein Beweissicherungsverfahren und für Pilar Pinilla zwei In-Situ-Speicher aktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="b0256-p108">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold. If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property. For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="b0256-141">Wenn viele In-Situ-Speicher für ein inaktives Postfach aktiviert werden, werden nicht alle In-Situ-Speicher-GUIDs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0256-141">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="b0256-142">Sie können den folgenden Befehl ausführen, um alle in-situ-Speicher-GUIDs anzuzeigen:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="b0256-142">You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="b0256-143">Schritt 2: Entfernen eines Haltebereichs von einem inaktiven Postfach</span><span class="sxs-lookup"><span data-stu-id="b0256-143">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="b0256-p110">Nachdem Sie ermittelt haben, welche Art von Haltebereich für das inaktive Postfach aktiviert ist (und ob es mehrere Haltebereiche gibt), werden im nächsten Schritt die Haltebereiche für das Postfach entfernt. Wie bereits erwähnt, müssen Sie alle Haltebereiche entfernen, um ein inaktives Postfach endgültig zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b0256-p110">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="b0256-146">Entfernen eines Beweissicherungsverfahrens</span><span class="sxs-lookup"><span data-stu-id="b0256-146">Remove a Litigation Hold</span></span>

<span data-ttu-id="b0256-p111">Wie bereits erwähnt, müssen Sie Windows PowerShell verwenden, um ein Beweissicherungsverfahren von einem inaktiven Postfach zu entfernen. Sie können nicht die EAC verwenden. Führen Sie den folgenden Befehl aus, um ein Beweissicherungsverfahren zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b0256-p111">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="b0256-p112">Die beste Methode zum Identifizieren eines inaktiven Postfachs ist die Verwendung des Distinguished Name oder des Exchange-GUID-Werts. Durch Verwenden eines dieser Werte können Sie verhindern, versehentlich das falsche Postfach anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b0256-p112">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="b0256-152">Entfernen von In-Situ-Speichern</span><span class="sxs-lookup"><span data-stu-id="b0256-152">Remove In-Place Holds</span></span>

 <span data-ttu-id="b0256-153">Es gibt zwei Möglichkeiten, um einen In-Situ-Speicher von einem inaktiven Postfach zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="b0256-153">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="b0256-154">**Löschen des in-situ-Aufbewahrungs Objekts** Wenn das inaktive Postfach, das Sie dauerhaft löschen möchten, das einzige Quellpostfach für einen in-situ-Speicher ist, können Sie einfach das in-situ-Speicherobjekt löschen.</span><span class="sxs-lookup"><span data-stu-id="b0256-154">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b0256-p113">Sie müssen den Haltebereich deaktivieren, bevor Sie ein In-Situ-Speicherobjekt löschen können. Wenn Sie versuchen, ein In-Situ-Speicherobjekt zu löschen, dessen Haltebereich aktiviert ist, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0256-p113">You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="b0256-157">**Entfernen des inaktiven Postfachs als Quellpostfach für einen In-Situ-Speicher** Wenn Sie andere Quellpostfächer für einen In-Situ-Speicher beibehalten möchten, können Sie das inaktive Postfach aus der Liste der Quellpostfächer entfernen und das In-Situ-Speicherobjekt beibehalten.</span><span class="sxs-lookup"><span data-stu-id="b0256-157">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="b0256-158">Verwenden der EAC zum Löschen eines In-Situ-Speichers</span><span class="sxs-lookup"><span data-stu-id="b0256-158">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="b0256-p114">Wenn Sie den Namen des zu löschenden In-Situ-Speichers kennen, können Sie mit dem nächsten Schritt fortfahren. Andernfalls führen Sie den folgenden Befehl aus, um den Namen des In-Situ-Speichers abzurufen, der für das endgültig zu löschende inaktive Postfach aktiviert ist. Verwenden Sie die In-Situ-Speicher-GUID, die Sie in [Schritt 1: Identifizieren der Haltebereiche für ein inaktives Postfach](#step-1-identify-the-holds-on-an-inactive-mailbox) abgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="b0256-p114">If you know the name of the In-Place Hold that you want to delete, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="b0256-162">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="b0256-162">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="b0256-163">Wählen Sie den in-situ-Speicher aus, den Sie löschen möchten \*\*\*\* ![, und klicken](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)Sie dann auf Bearbeitungssymbol bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b0256-163">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="b0256-164">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="b0256-164">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="b0256-165">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span><span class="sxs-lookup"><span data-stu-id="b0256-165">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="b0256-166">Klicken Sie in der Warnung auf **Ja**, um den In-Situ-Speicher zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b0256-166">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="b0256-167">Verwenden von Exchange Online PowerShell zum Löschen eines In-Situ-Speichers</span><span class="sxs-lookup"><span data-stu-id="b0256-167">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="b0256-p115">Erstellen Sie eine Variable, die die Eigenschaften des zu löschenden In-Situ-Speichers enthält. Verwenden Sie die In-Situ-Speicher-GUID, die Sie in [Schritt 1: Identifizieren der Haltebereiche für ein inaktives Postfach](#step-1-identify-the-holds-on-an-inactive-mailbox) abgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="b0256-p115">Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="b0256-170">Deaktivieren Sie den Haltebereich für den In-Situ-Speicher.</span><span class="sxs-lookup"><span data-stu-id="b0256-170">Disable the hold on the In-Place Hold.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="b0256-171">Löschen Sie den In-Situ-Speicher.</span><span class="sxs-lookup"><span data-stu-id="b0256-171">Delete the In-Place Hold.</span></span>
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="b0256-172">Verwenden der EAC zum Entfernen eines inaktiven Postfachs aus einem In-Situ-Speicher</span><span class="sxs-lookup"><span data-stu-id="b0256-172">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="b0256-p116">Wenn Sie den Namen des In-Situ-Speichers kennen, der dem inaktiven Postfach zugeordnet ist, können Sie mit dem nächsten Schritt fortfahren. Führen Sie andernfalls den folgenden Befehl aus, um den Namen des In-Situ-Speichers abzurufen, der dem Postfach zugeordnet ist. Verwenden Sie die In-Situ-Speicher-GUID, die Sie in [Schritt 1: Identifizieren der Haltebereiche für ein inaktives Postfach](#step-1-identify-the-holds-on-an-inactive-mailbox) abgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="b0256-p116">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step. Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="b0256-176">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span><span class="sxs-lookup"><span data-stu-id="b0256-176">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="b0256-177">Wählen Sie den in-situ-Speicher aus, der in dem inaktiven Postfach \*\*\*\* ![platziert wird,](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)und klicken Sie dann auf Bearbeitungssymbol bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b0256-177">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="b0256-178">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span><span class="sxs-lookup"><span data-stu-id="b0256-178">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="b0256-179">Klicken Sie in der Liste der Quellpostfächer auf den Namen des inaktiven Postfachs, das Sie entfernen möchten, und dann auf **Entfernen**![Entfernen (Symbol)](media/adf01106-cc79-475c-8673-065371c1897b.gif).</span><span class="sxs-lookup"><span data-stu-id="b0256-179">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="b0256-p117">Klicken Sie zum Speichern der Änderung auf **Speichern**. Eine Meldung wird angezeigt, dass der Vorgang erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="b0256-p117">Click **Save** to save the change. A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="b0256-182">Wiederholen Sie die Schritte 1 bis 6, um andere In-Situ-Speicher zu entfernen, die dem inaktiven Postfach zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b0256-182">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="b0256-183">Verwenden der Exchange Online PowerShell zum Entfernen eines inaktiven Postfachs aus einem In-Situ-Speicher</span><span class="sxs-lookup"><span data-stu-id="b0256-183">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="b0256-p118">Wenn der In-Situ-Speicher eine große Anzahl von Postfächern enthält, ist das inaktive Postfach möglicherweise nicht auf der Seite **Quellen** in der Exchange-Verwaltungskonsole aufgelistet. Bis zu 3.000 Postfächer werden auf der Seite **Quellen** angezeigt, wenn Sie einen In-Situ-Speicher bearbeiten. Wenn ein inaktives Postfach nicht auf der Seite **Quellen** aufgelistet ist, können Sie Exchange Online PowerShell verwenden, um es aus dem In-Situ-Speicher zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b0256-p118">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC. Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold. If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="b0256-p119">Erstellen Sie eine Variable, die die Eigenschaften des In-Situ-Speichers enthält, der dem inaktiven Postfach zugeordnet ist. Verwenden Sie die In-Situ-Speicher-GUID, die Sie in [Schritt 1: Identifizieren der Haltebereiche für ein inaktives Postfach](#step-1-identify-the-holds-on-an-inactive-mailbox) abgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="b0256-p119">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="b0256-189">Stellen Sie sicher, dass das inaktive Postfach als ein Quellpostfach für den In-Situ-Speicher aufgelistet ist.</span><span class="sxs-lookup"><span data-stu-id="b0256-189">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   <span data-ttu-id="b0256-190">**Hinweis:** Die *Sources-Eigenschaft des* in-situ-Speichers identifiziert die Quellpostfächer nach Ihren *legacyExchangeDN* -Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="b0256-190">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="b0256-191">Da diese Eigenschaft inaktive Postfächer eindeutig identifiziert, können Sie mit der Eigenschaft *Sources* des In-Situ-Speichers verhindern, das falsche Postfach zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b0256-191">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="b0256-192">Außerdem vermeiden Sie auch Probleme, wenn zwei Postfächer über denselben Alias oder dieselbe SMTP-Adresse verfügen.</span><span class="sxs-lookup"><span data-stu-id="b0256-192">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="b0256-p121">Entfernen Sie das inaktive Postfach aus der Liste der Quellpostfächer in der Variablen. Achten Sie darauf, die Eigenschaft **LegacyExchangeDN** des inaktiven Postfachs zu verwenden, die von dem Befehl im vorherigen Schritt zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b0256-p121">Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="b0256-195">Der folgende Befehl entfernt z. B. das inaktive Postfach für Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="b0256-195">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="b0256-196">Stellen Sie sicher, dass das inaktive Postfach aus der Liste der Quellpostfächer in der Variable entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="b0256-196">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="b0256-197">Ändern Sie den In-Situ-Speicher mit der aktualisierten Liste der Quellpostfächer, die das inaktive Postfach nicht enthält.</span><span class="sxs-lookup"><span data-stu-id="b0256-197">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="b0256-198">Stellen Sie sicher, dass das inaktive Postfach aus der Liste der Quellpostfächer für den In-Situ-Speicher entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="b0256-198">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="b0256-199">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0256-199">More information</span></span>

- <span data-ttu-id="b0256-p122">**Ein inaktives Postfach ist ein Typ des vorläufig gelöschten Postfachs.** In Exchange Online ist ein vorläufig gelöschtes Postfach, das zwar gelöscht wurde, aber innerhalb einer bestimmten Beibehaltungsdauer wiederhergestellt werden kann. Die Aufbewahrungsdauer für vorläufig gelöschte Postfächer beträgt in Exchange Online 30 Tage. Das bedeutet, dass das Postfach innerhalb von 30 Tagen nach dem vorläufigen Löschen wiederhergestellt werden kann. Nach 30 Tagen wird ein vorläufig gelöschtes Postfach zum dauerhaften Löschen markiert und kann nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="b0256-p122">**An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="b0256-p123">**Was geschieht, nachdem Sie den Haltebereich für ein inaktives Postfach entfernt haben?** Das Postfach wird wie andere vorläufig gelöschte Postfächer behandelt und wird für die dauerhafte Löschung markiert, nachdem die 30-tägige Beibehaltungsdauer für das vorläufig gelöschte Postfach abgelaufen ist. Dieser Aufbewahrungszeitraum beginnt an dem Datum, an dem das Postfach erstmals inaktiv gemacht wurde. Dieses Datum wird als Datum für das vorläufige Löschen bezeichnet und ist das Datum, an dem das entsprechende Office 365-Benutzerkonto oder an dem das Exchange Online-Postfach mit dem Cmdlet **Remove-Mailbox** gelöscht wurde. Das Datum für das vorläufige Löschen ist nicht das Datum, an dem Sie den Haltebereich entfernt haben.</span><span class="sxs-lookup"><span data-stu-id="b0256-p123">**What happens after you remove the hold on an inactive mailbox?** The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires. This retention period starts on the date when the mailbox was first made inactive. This date is known as the soft-deleted date, which is the date the corresponding Office 365 user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet. The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="b0256-p124">**Wird ein inaktives Postfach sofort nach dem Entfernen des Haltebereichs dauerhaft gelöscht?** Wenn das Datum für vorläufig gelöschte Elemente für ein inaktives Postfach mehr als 30 Tage zurückliegt, wird das Postfach nicht sofort dauerhaft gelöscht, sobald Sie den Haltebereich entfernen. Das Postfach wird zum endgültigen Löschen markiert und bei der nächsten Verarbeitung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b0256-p124">**Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="b0256-213">**Wie wirkt sich die Beibehaltungsdauer für das vorläufig gelöschte Postfach auf inaktive Postfächer aus?**</span><span class="sxs-lookup"><span data-stu-id="b0256-213">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="b0256-214">Wenn das Datum für vorläufig gelöschte Elemente für ein inaktives Postfach über 30 Tage vor dem Datum liegt, an dem der Haltebereich entfernt wurde, wird das Postfach für die dauerhafte Löschung markiert.</span><span class="sxs-lookup"><span data-stu-id="b0256-214">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="b0256-215">Wenn jedoch ein inaktives Postfach über ein Datum für das vorläufige Löschen innerhalb der letzten 30 Tage verfügt und Sie den Haltebereich entfernen, können Sie das Postfach bis zum Ablauf des Aufbewahrungszeitraums für das vorläufige Löschen wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="b0256-215">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="b0256-216">Ausführliche Informationen finden Sie unter [Löschen oder Wiederherstellen von Benutzerpostfächern in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span><span class="sxs-lookup"><span data-stu-id="b0256-216">For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span></span> <span data-ttu-id="b0256-217">Nachdem die Beibehaltungsdauer für das vorläufig gelöschte Postfach abgelaufen ist, müssen Sie die Prozeduren für das Wiederherstellen eines inaktiven Postfachs befolgen.</span><span class="sxs-lookup"><span data-stu-id="b0256-217">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="b0256-218">Ausführliche Informationen finden Sie unter [Wiederherstellen eines inaktiven Postfachs in Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="b0256-218">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="b0256-219">**Wie können Informationen über ein inaktives Postfach angezeigt werden, nachdem der Haltebereich entfernt wurde?**</span><span class="sxs-lookup"><span data-stu-id="b0256-219">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="b0256-220">Nachdem ein Haltestatus entfernt wurde und das inaktive Postfach wieder auf ein vorläufig gelöschtes Postfach zurückgesetzt wird, wird es nicht mithilfe des *InactiveMailboxOnly* -Parameters mit dem Cmdlet **Get-Mailbox** zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b0256-220">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="b0256-221">Sie können jedoch Informationen über das Postfach anzeigen, indem Sie den Befehl **Get-Mailbox -SoftDeletedMailbox** verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0256-221">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="b0256-222">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b0256-222">For example:</span></span> 
    
  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
  ```

  <span data-ttu-id="b0256-223">Im obigen Beispiel gibt die *WhenSoftDeleted* -Eigenschaft das vorläufig gelöschte Datum an, das in diesem Beispiel 30. Oktober 2014 ist.</span><span class="sxs-lookup"><span data-stu-id="b0256-223">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="b0256-224">Wenn es sich bei diesem vorläufig gelöschten Postfach um ein inaktives Postfach handelte, für das der Haltebereich entfernt wurde, wird es 30 Tage nach dem Wert der *WhenSoftDeleted* -Eigenschaft endgültig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b0256-224">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="b0256-225">In diesem Fall wird das Postfach nach dem 30. November 2014 endgültig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b0256-225">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

