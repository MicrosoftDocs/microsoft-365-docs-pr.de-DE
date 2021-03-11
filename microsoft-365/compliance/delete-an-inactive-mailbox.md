---
title: Löschen eines inaktiven Postfachs
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Wenn Sie den Inhalt eines inaktiven Microsoft 365-Postfachs nicht mehr beibehalten müssen, können Sie das inaktive Postfach dauerhaft löschen.
ms.openlocfilehash: d5acccbf37ee5b6958d282de14edafc0b9b00182
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717579"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="6f1d8-103">Löschen eines inaktiven Postfachs</span><span class="sxs-lookup"><span data-stu-id="6f1d8-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="6f1d8-104">Ein inaktives Postfach wird verwendet, um die E-Mails eines ehemaligen Mitarbeiters zu erhalten, nachdem sie Ihre Organisation verlassen haben.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-104">An inactive mailbox is used to preserve a former employee's email after they leave your organization.</span></span> <span data-ttu-id="6f1d8-105">Wenn Sie die Inhalte eines inaktiven Postfachs nicht mehr aufbewahren müssen, können Sie das inaktive Postfach durch Entfernen des Haltebereichs endgültig löschen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="6f1d8-106">Darüber hinaus ist es möglich, mehrere Haltebereiche für ein inaktives Postfach festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="6f1d8-107">Beispielsweise kann für ein inaktives Postfach ein Beweissicherungsverfahren aktiviert oder das Postfach in einem oder mehreren In-Situ-Speichern abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="6f1d8-108">Darüber hinaus kann eine Aufbewahrungsrichtlinie (erstellt im Security and Compliance Center in Office 365 oder Microsoft 365) auf das inaktive Postfach angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="6f1d8-109">Sie müssen alle Aufbewahrungs- und Aufbewahrungsrichtlinien aus einem inaktiven Postfach entfernen, um es zu löschen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="6f1d8-110">Nach dem Entfernen der Haltebereiche und Aufbewahrungsrichtlinien wird das inaktive Postfach zum Löschen markiert und endgültig gelöscht, nachdem es verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6f1d8-111">Da wir weiterhin auf unterschiedliche Weise investieren, um Postfachinhalte zu erhalten, wird der In-Place im Exchange Admin Center angekündigt.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="6f1d8-112">Das bedeutet, dass Sie zum Erstellen eines inaktiven Postfachs Aufbewahrungs- und Aufbewahrungsrichtlinien verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="6f1d8-113">Ab dem 1. Juli 2020 können Sie keine neuen In-Place in Exchange Online erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="6f1d8-114">Sie können jedoch weiterhin die Haltedauer eines In-Place inaktiven Postfachs ändern.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="6f1d8-115">Ab dem 1. Oktober 2020 können Sie die Haltedauer jedoch nicht mehr ändern.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="6f1d8-116">Sie können nur ein inaktives Postfach löschen, indem Sie die In-Place entfernen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="6f1d8-117">Vorhandene inaktive Postfächer, die sich im In-Place befinden, bleiben bis zum Entfernen des Haltespeichers erhalten.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="6f1d8-118">Weitere Informationen zum Austritt von In-Place finden Sie unter [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span><span class="sxs-lookup"><span data-stu-id="6f1d8-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="6f1d8-119">Eine Beschreibung dessen, was geschieht, wenn Haltebereiche von einem inaktiven Postfach entfernt werden, finden Sie im Abschnitt [Weitere Informationen](#more-information).</span><span class="sxs-lookup"><span data-stu-id="6f1d8-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="6f1d8-120">Vor dem Löschen eines inaktiven Postfachs</span><span class="sxs-lookup"><span data-stu-id="6f1d8-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="6f1d8-121">Sie müssen Exchange Online PowerShell zum Entfernen eines Beweissicherungsverfahrens für ein inaktives Postfach verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="6f1d8-122">Sie können nicht die Exchange-Verwaltungskonsole (EAC) verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="6f1d8-123">Schrittweise Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="6f1d8-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="6f1d8-124">Sie können die Inhalte eines inaktiven Postfachs in ein anderes Postfach kopieren, bevor Sie den Haltebereich entfernen und ein inaktives Postfach löschen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-124">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="6f1d8-125">Weitere Informationen finden Sie unter [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="6f1d8-125">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="6f1d8-126">Wenn Sie die Aufbewahrungs- oder Aufbewahrungsrichtlinie aus einem inaktiven Postfach entfernen und der Aufbewahrungszeitraum für das dauerhaft gelöschte Postfach für das Postfach abgelaufen ist, wird das Postfach endgültig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-126">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="6f1d8-127">Nachdem es gelöscht wurde, kann es nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-127">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="6f1d8-128">Stellen Sie vor dem Entfernen des Haltebereichs sicher, dass Sie die Inhalte im Postfach nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-128">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="6f1d8-129">Wenn Sie ein inaktives Postfach reaktivieren möchten, können Sie es wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-129">If you want to reactivate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="6f1d8-130">Weitere Informationen finden Sie unter [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="6f1d8-130">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="6f1d8-131">Weitere Informationen zu inaktiven Postfächern finden Sie unter [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="6f1d8-131">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="6f1d8-132">Schritt 1: Identifizieren der Haltebereiche für ein inaktives Postfach</span><span class="sxs-lookup"><span data-stu-id="6f1d8-132">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="6f1d8-133">Wie bereits erwähnt, kann für ein inaktives Postfach In-Place Aufbewahrungs- oder Aufbewahrungsrichtlinie für Rechtsstreitigkeiten aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-133">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="6f1d8-134">Der erste Schritt besteht darin, die Haltebereiche für ein inaktives Postfach zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-134">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="6f1d8-135">Führen Sie den folgenden Befehl aus, um die Informationen zu Haltebereichen für alle inaktiven Postfächer in Ihrer Organisation anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-135">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="6f1d8-136">Der Wert **True** für die Eigenschaft **LitigationHoldEnabled** gibt an, dass für das inaktive Postfach ein Beweissicherungsverfahren aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-136">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="6f1d8-137">Wenn ein In-Situ-Speicher für ein inaktives Postfach aktiviert ist, wird die GUID für den Haltebereich als Wert für die Eigenschaft **InPlaceHolds** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-137">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="6f1d8-138">Die folgenden Ergebnisse für zwei inaktive Postfächer zeigen beispielsweise, dass ann Beebe ein Prozessaufbewahrungsverfahren besteht und dass eine In-Place-Aufbewahrungs- und Aufbewahrungsrichtlinie auf Pilar Pinilla gesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-138">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that an In-Place Hold and retention policy are placed on Pilar Pinilla.</span></span>
  
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
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="6f1d8-139">Wenn viele In-Place oder Aufbewahrungsrichtlinien für ein inaktives Postfach platziert werden, werden nicht alle In-Place-GUIDs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-139">If a lot of In-Place Holds or retention policies are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="6f1d8-140">Sie können den folgenden Befehl ausführen, um alle GUIDs in der InPlaceHolds-Eigenschaft anzeigen:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="6f1d8-140">You can run the following command to display all the GUIDs in the InPlaceHolds property:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
<span data-ttu-id="6f1d8-141">Weitere Informationen zum Identifizieren von Haltefächern finden Sie unter [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="6f1d8-141">For more information about identify holds, see [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="6f1d8-142">Schritt 2: Entfernen eines Haltebereichs von einem inaktiven Postfach</span><span class="sxs-lookup"><span data-stu-id="6f1d8-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="6f1d8-p109">Nachdem Sie ermittelt haben, welche Art von Haltebereich für das inaktive Postfach aktiviert ist (und ob es mehrere Haltebereiche gibt), werden im nächsten Schritt die Haltebereiche für das Postfach entfernt. Wie bereits erwähnt, müssen Sie alle Haltebereiche entfernen, um ein inaktives Postfach endgültig zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-p109">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox. As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span>
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="6f1d8-145">Entfernen eines Beweissicherungsverfahrens</span><span class="sxs-lookup"><span data-stu-id="6f1d8-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="6f1d8-p110">Wie bereits erwähnt, müssen Sie Windows PowerShell verwenden, um ein Beweissicherungsverfahren von einem inaktiven Postfach zu entfernen. Sie können nicht die EAC verwenden. Führen Sie den folgenden Befehl aus, um ein Beweissicherungsverfahren zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-p110">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox. You can't use the EAC. Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="6f1d8-p111">Die beste Methode zum Identifizieren eines inaktiven Postfachs ist die Verwendung des Distinguished Name oder des Exchange-GUID-Werts. Durch Verwenden eines dieser Werte können Sie verhindern, versehentlich das falsche Postfach anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-p111">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value. Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a><span data-ttu-id="6f1d8-151">Entfernen eines inaktiven Postfachs aus einer Aufbewahrungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6f1d8-151">Remove an inactive mailbox from a retention policy</span></span>

<span data-ttu-id="6f1d8-152">Das Verfahren zum Entfernen eines inaktiven Postfachs aus einer Microsoft 365-Aufbewahrungsrichtlinie hängt davon ab, ob die dem inaktiven Postfach zugewiesene Aufbewahrungsrichtlinie organisationsweit oder explizit ist.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-152">The procedure to remove an inactive mailbox from a Microsoft 365 retention policy depends whether the retention policy assigned to the inactive mailbox is organization-wide or explicit.</span></span> <span data-ttu-id="6f1d8-153">für den Typ der Aufbewahrungsrichtlinie, die dem inaktiven Postfach zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-153">on the type of retention policy that's assigned to the inactive mailbox.</span></span>

- <span data-ttu-id="6f1d8-154">Organisationsweite Aufbewahrungsrichtlinien, die allen Postfächern in der Organisation zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-154">Organization-wide retention policies assigned to all mailboxes in the organization.</span></span> <span data-ttu-id="6f1d8-155">Verwenden Sie **das Cmdlet Get-OrganizationConfig** in Exchange Online PowerShell, um Informationen zu organisationsweiten Aufbewahrungsrichtlinien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-155">Use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span>

- <span data-ttu-id="6f1d8-156">Bestimmte Aufbewahrungsrichtlinien für Speicherorte, die bestimmten Postfächern zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-156">Specific location retention policies assigned to specific mailboxes.</span></span> <span data-ttu-id="6f1d8-157">Dies sind Richtlinien, die den Inhaltsstandorten bestimmter Benutzer zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-157">These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="6f1d8-158">Verwenden Sie **das Cmdlet Get-Mailbox -IncludeInactiveMailbox** in Exchange Online PowerShell, um Informationen zu Aufbewahrungsrichtlinien zu erhalten, die bestimmten inaktiven Postfächern zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-158">Use the **Get-Mailbox -IncludeInactiveMailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific inactive mailboxes.</span></span>

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a><span data-ttu-id="6f1d8-159">Entfernen eines inaktiven Postfachs aus einer organisationsweiten Aufbewahrungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6f1d8-159">Remove an inactive mailbox from an organization-wide retention policy</span></span>

<span data-ttu-id="6f1d8-160">Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um ein inaktives Postfach aus einer organisationsweiten Aufbewahrungsrichtlinie auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-160">Run the following command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide retention policy.</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

<span data-ttu-id="6f1d8-161">Weitere Informationen zur Identifizierung organisationsweiter Aufbewahrungsrichtlinien, die auf ein inaktives Postfach angewendet werden, und zum Abrufen der GUID für eine Aufbewahrungsrichtlinie finden Sie im Abschnitt "Get-OrganizationConfig" unter [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig).</span><span class="sxs-lookup"><span data-stu-id="6f1d8-161">For more information identifying organization-wide retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-OrganizationConfig" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig).</span></span>

<span data-ttu-id="6f1d8-162">Alternativ können Sie den folgenden Befehl ausführen, um das inaktive Postfach aus allen organisationsweiten Richtlinien zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="6f1d8-162">Alternatively, you can run the following command to remove the inactive mailbox from all organization-wide policies:</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a><span data-ttu-id="6f1d8-163">Entfernen eines inaktiven Postfachs aus einer bestimmten Aufbewahrungsrichtlinie für Speicherorte</span><span class="sxs-lookup"><span data-stu-id="6f1d8-163">Remove an inactive mailbox from a specific location retention policy</span></span>

<span data-ttu-id="6f1d8-164">Führen Sie den folgenden Befehl in [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) aus, um ein inaktives Postfach aus einer expliziten Aufbewahrungsrichtlinie zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-164">Run the following command in [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) to remove an inactive mailbox from an explicit retention policy.</span></span>

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

<span data-ttu-id="6f1d8-165">Weitere Informationen zum Identifizieren bestimmter Aufbewahrungsrichtlinien für Speicherorte, die auf ein inaktives Postfach angewendet werden, und zum Abrufen der GUID für eine Aufbewahrungsrichtlinie finden Sie im Abschnitt "Get-Mailbox" unter [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox).</span><span class="sxs-lookup"><span data-stu-id="6f1d8-165">For more information identifying specific location retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-Mailbox" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox).</span></span>

### <a name="remove-in-place-holds"></a><span data-ttu-id="6f1d8-166">Entfernen der In-Situ-Aufbewahrung</span><span class="sxs-lookup"><span data-stu-id="6f1d8-166">Remove In-Place Holds</span></span>

 <span data-ttu-id="6f1d8-167">Es gibt zwei Möglichkeiten, um einen In-Situ-Speicher von einem inaktiven Postfach zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="6f1d8-167">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="6f1d8-168">**Löschen sie In-Place Hold-Objekt**.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-168">**Delete the In-Place Hold object**.</span></span> <span data-ttu-id="6f1d8-169">Wenn das inaktive Postfach, das Sie dauerhaft löschen möchten, das einzige Quellpostfach für ein In-Place-Archiv ist, können Sie einfach das In-Place löschen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-169">If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="6f1d8-p116">Sie müssen den Haltebereich deaktivieren, bevor Sie ein In-Situ-Speicherobjekt löschen können. Wenn Sie versuchen, ein In-Situ-Speicherobjekt zu löschen, dessen Haltebereich aktiviert ist, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-p116">You have to disable the hold before you can delete an In-Place Hold object. If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="6f1d8-172">**Entfernen Sie das inaktive Postfach als Quellpostfach eines In-Place Archivs.**</span><span class="sxs-lookup"><span data-stu-id="6f1d8-172">**Remove the inactive mailbox as a source mailbox of an In-Place Hold**.</span></span> <span data-ttu-id="6f1d8-173">Wenn Sie andere Quellpostfächer für einen In-Place beibehalten möchten, können Sie das inaktive Postfach aus der Liste der Quellpostfächer entfernen und das In-Place beibehalten.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-173">If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span>

#### <a name="delete-an-in-place-hold"></a><span data-ttu-id="6f1d8-174">Löschen eines In-Place-Halte</span><span class="sxs-lookup"><span data-stu-id="6f1d8-174">Delete an In-Place Hold</span></span>

1. <span data-ttu-id="6f1d8-p118">Erstellen Sie eine Variable, die die Eigenschaften des zu löschenden In-Situ-Speichers enthält. Verwenden Sie die In-Situ-Speicher-GUID, die Sie in [Schritt 1: Identifizieren der Haltebereiche für ein inaktives Postfach](#step-1-identify-the-holds-on-an-inactive-mailbox) abgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-p118">Create a variable that contains the properties of the In-Place Hold that you want to delete. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="6f1d8-177">Deaktivieren Sie den Haltebereich für den In-Situ-Speicher.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-177">Disable the hold on the In-Place Hold.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="6f1d8-178">Löschen Sie den In-Situ-Speicher.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-178">Delete the In-Place Hold.</span></span>

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="6f1d8-179">Entfernen eines inaktiven Postfachs aus In-Place Archiv</span><span class="sxs-lookup"><span data-stu-id="6f1d8-179">Remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="6f1d8-p119">Wenn der In-Situ-Speicher eine große Anzahl von Postfächern enthält, ist das inaktive Postfach möglicherweise nicht auf der Seite **Quellen** in der Exchange-Verwaltungskonsole aufgelistet. Bis zu 3.000 Postfächer werden auf der Seite **Quellen** angezeigt, wenn Sie einen In-Situ-Speicher bearbeiten. Wenn ein inaktives Postfach nicht auf der Seite **Quellen** aufgelistet ist, können Sie Exchange Online PowerShell verwenden, um es aus dem In-Situ-Speicher zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-p119">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC. Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold. If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="6f1d8-p120">Erstellen Sie eine Variable, die die Eigenschaften des In-Situ-Speichers enthält, der dem inaktiven Postfach zugeordnet ist. Verwenden Sie die In-Situ-Speicher-GUID, die Sie in [Schritt 1: Identifizieren der Haltebereiche für ein inaktives Postfach](#step-1-identify-the-holds-on-an-inactive-mailbox) abgerufen haben.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-p120">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox. Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="6f1d8-185">Stellen Sie sicher, dass das inaktive Postfach als ein Quellpostfach für den In-Situ-Speicher aufgelistet ist.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-185">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > <span data-ttu-id="6f1d8-p121">Die Eigenschaft *Sources* des In-Situ-Speichers identifiziert die Quellpostfächer nach der Eigenschaft *LegacyExchangeDN*. Da diese Eigenschaft inaktive Postfächer eindeutig identifiziert, können Sie mit der Eigenschaft *Sources* des In-Situ-Speichers verhindern, das falsche Postfach zu entfernen. Außerdem vermeiden Sie auch Probleme, wenn zwei Postfächer über denselben Alias oder dieselbe SMTP-Adresse verfügen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-p121">The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties. Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox. This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 

3. <span data-ttu-id="6f1d8-p122">Entfernen Sie das inaktive Postfach aus der Liste der Quellpostfächer in der Variablen. Achten Sie darauf, die Eigenschaft **LegacyExchangeDN** des inaktiven Postfachs zu verwenden, die von dem Befehl im vorherigen Schritt zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-p122">Remove the inactive mailbox from the list of source mailboxes in the variable. Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="6f1d8-191">Der folgende Befehl entfernt z. B. das inaktive Postfach für Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-191">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="6f1d8-192">Stellen Sie sicher, dass das inaktive Postfach aus der Liste der Quellpostfächer in der Variable entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-192">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>

   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="6f1d8-193">Ändern Sie den In-Situ-Speicher mit der aktualisierten Liste der Quellpostfächer, die das inaktive Postfach nicht enthält.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-193">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="6f1d8-194">Stellen Sie sicher, dass das inaktive Postfach aus der Liste der Quellpostfächer für den In-Situ-Speicher entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-194">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="6f1d8-195">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f1d8-195">More information</span></span>

- <span data-ttu-id="6f1d8-p123">**Ein inaktives Postfach ist ein Typ des vorläufig gelöschten Postfachs.** In Exchange Online ist ein vorläufig gelöschtes Postfach, das zwar gelöscht wurde, aber innerhalb einer bestimmten Beibehaltungsdauer wiederhergestellt werden kann. Die Aufbewahrungsdauer für vorläufig gelöschte Postfächer beträgt in Exchange Online 30 Tage. Das bedeutet, dass das Postfach innerhalb von 30 Tagen nach dem vorläufigen Löschen wiederhergestellt werden kann. Nach 30 Tagen wird ein vorläufig gelöschtes Postfach zum dauerhaften Löschen markiert und kann nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-p123">**An inactive mailbox is a type of soft-deleted mailbox.** In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period. The soft-deleted mailbox retention period in Exchange Online is 30 days. This means that the mailbox can be recovered within 30 days of being soft-deleted. After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span>

- <span data-ttu-id="6f1d8-201">**Was geschieht, nachdem Sie den Haltebereich für ein inaktives Postfach entfernt haben?**</span><span class="sxs-lookup"><span data-stu-id="6f1d8-201">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="6f1d8-202">Das Postfach wird wie andere vorläufig gelöschte Postfächer behandelt und wird für die dauerhafte Löschung markiert, nachdem die 30-tägige Beibehaltungsdauer für das vorläufig gelöschte Postfach abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-202">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="6f1d8-203">Dieser Aufbewahrungszeitraum beginnt an dem Datum, an dem das Postfach erstmals inaktiv gemacht wurde.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-203">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="6f1d8-204">Dieses Datum wird als datumsaktiv gelöscht bezeichnet, d. h. das Datum, an dem das entsprechende Benutzerkonto gelöscht wurde oder das Exchange Online-Postfach mit dem **Cmdlet Remove-Mailbox** gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-204">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="6f1d8-205">Das Datum für das vorläufige Löschen ist nicht das Datum, an dem Sie den Haltebereich entfernt haben.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-205">The soft-deleted date isn't the date on which you remove the hold.</span></span>

- <span data-ttu-id="6f1d8-p125">**Wird ein inaktives Postfach sofort nach dem Entfernen des Haltebereichs dauerhaft gelöscht?** Wenn das Datum für vorläufig gelöschte Elemente für ein inaktives Postfach mehr als 30 Tage zurückliegt, wird das Postfach nicht sofort dauerhaft gelöscht, sobald Sie den Haltebereich entfernen. Das Postfach wird zum endgültigen Löschen markiert und bei der nächsten Verarbeitung gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-p125">**Is an inactive mailbox permanently deleted immediately after the hold is removed?** If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold. The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span>

- <span data-ttu-id="6f1d8-209">**Wie wirkt sich die Beibehaltungsdauer für das vorläufig gelöschte Postfach auf inaktive Postfächer aus?**</span><span class="sxs-lookup"><span data-stu-id="6f1d8-209">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="6f1d8-210">Wenn das Datum für vorläufig gelöschte Elemente für ein inaktives Postfach über 30 Tage vor dem Datum liegt, an dem der Haltebereich entfernt wurde, wird das Postfach für die dauerhafte Löschung markiert.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-210">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="6f1d8-211">Wenn jedoch ein inaktives Postfach über ein Datum für das vorläufige Löschen innerhalb der letzten 30 Tage verfügt und Sie den Haltebereich entfernen, können Sie das Postfach bis zum Ablauf des Aufbewahrungszeitraums für das vorläufige Löschen wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-211">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="6f1d8-212">Weitere Informationen finden Sie unter [Löschen oder Wiederherstellen von Benutzerpostfächern in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="6f1d8-212">For details, see [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes).</span></span> <span data-ttu-id="6f1d8-213">Nach Ablauf des Aufbewahrungszeitraums für weiche gelöschte Postfächer müssen Sie die Verfahren zum Wiederherstellen eines inaktiven Postfachs befolgen.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-213">After the soft-deleted mailbox retention period expires, you have to follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="6f1d8-214">Weitere Informationen finden Sie unter [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="6f1d8-214">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="6f1d8-215">**Wie können Informationen über ein inaktives Postfach angezeigt werden, nachdem der Haltebereich entfernt wurde?**</span><span class="sxs-lookup"><span data-stu-id="6f1d8-215">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="6f1d8-216">Nachdem ein Haltefeld entfernt wurde und das inaktive Postfach wieder auf ein soft-deleted-Postfach zurückgesetzt wurde, wird es nicht mithilfe des  *Parameters InactiveMailboxOnly*  mit dem **Cmdlet Get-Mailbox** zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-216">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="6f1d8-217">Sie können jedoch Informationen über das Postfach anzeigen, indem Sie den Befehl **Get-Mailbox -SoftDeletedMailbox** verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-217">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="6f1d8-218">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6f1d8-218">For example:</span></span>

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

  <span data-ttu-id="6f1d8-219">Im obigen Beispiel identifiziert die *WhenSoftDeleted-Eigenschaft* das datumsweich gelöschte Datum, das in diesem Beispiel den 30. Oktober 2014 ist.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-219">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="6f1d8-220">Wenn dieses unbefristete Postfach zuvor ein inaktives Postfach war, für das das Archiv entfernt wurde, wird es 30 Tage nach dem Wert der *WhenSoftDeleted-Eigenschaft* endgültig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-220">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="6f1d8-221">In diesem Fall wird das Postfach nach dem 30. November 2014 endgültig gelöscht.</span><span class="sxs-lookup"><span data-stu-id="6f1d8-221">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>
