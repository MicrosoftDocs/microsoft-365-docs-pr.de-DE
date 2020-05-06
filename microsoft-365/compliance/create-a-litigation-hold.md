---
title: Erstellen einer Aufbewahrung für juristische Zwecke
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: Hier erfahren Sie, wie Sie ein Postfach auf das Beweissicherungsverfahren setzen und während einer Untersuchung alle Postfachinhalte beibehalten.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3ea5c07065788e342edcd0b5c70ef9dcaae48e16
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035817"
---
# <a name="create-a-litigation-hold"></a><span data-ttu-id="37ff6-103">Erstellen einer Aufbewahrung für juristische Zwecke</span><span class="sxs-lookup"><span data-stu-id="37ff6-103">Create a Litigation Hold</span></span>

<span data-ttu-id="37ff6-104">Sie können ein Postfach auf das Beweissicherungsverfahren setzen, um alle Postfachinhalte einschließlich der gelöschten Elemente und der ursprünglichen Versionen geänderter Elemente beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="37ff6-104">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items.</span></span> <span data-ttu-id="37ff6-105">Wenn Sie ein Benutzerpostfach auf das Beweissicherungsverfahren setzen, wird der Inhalt im Archivpostfach des Benutzers (sofern aktiviert) ebenfalls beibehalten.</span><span class="sxs-lookup"><span data-stu-id="37ff6-105">When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained.</span></span> <span data-ttu-id="37ff6-106">Wenn Sie einen Haltestatus erstellen, können Sie eine Aufbewahrungsdauer angeben (auch als *zeitbasierter Haltestatus*bezeichnet), sodass gelöschte und geänderte Elemente für einen bestimmten Zeitraum aufbewahrt und dann endgültig aus dem Postfach gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="37ff6-106">When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox.</span></span> <span data-ttu-id="37ff6-107">Oder Sie können Inhalte auf unbestimmte Zeit beibehalten (als *endlos Sperre*bezeichnet) oder bis das Beweissicherungsverfahren entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="37ff6-107">Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed.</span></span> <span data-ttu-id="37ff6-108">Wenn Sie einen Zeitraum für die Aufbewahrungsdauer angeben, wird er ab dem Datum berechnet, an dem eine Nachricht empfangen oder ein Postfachelement erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="37ff6-108">If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="37ff6-109">Hier erfahren Sie, was passiert, wenn Sie ein Beweissicherungsverfahren erstellen.</span><span class="sxs-lookup"><span data-stu-id="37ff6-109">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="37ff6-110">Elemente, die vom Benutzer dauerhaft gelöscht werden, werden für die Dauer des Haltestatus im Ordner "refundable Items" im Postfach des Benutzers aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="37ff6-110">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>
    
- <span data-ttu-id="37ff6-111">Elemente, die vom Benutzer aus dem Ordner "refundable Items" gelöscht werden, werden für die Dauer des Haltestatus aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="37ff6-111">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>
    
- <span data-ttu-id="37ff6-112">Das Speicherkontingent für den Ordner "refundable Items" wird von 30 GB auf 110 GB erhöht.</span><span class="sxs-lookup"><span data-stu-id="37ff6-112">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>
    
- <span data-ttu-id="37ff6-113">Elemente in der primären und der Archivpostfächer des Benutzers werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="37ff6-113">Items in the user's primary and the archive mailboxes are retained</span></span>
    
## <a name="before-you-begin"></a><span data-ttu-id="37ff6-114">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="37ff6-114">Before you begin</span></span>

- <span data-ttu-id="37ff6-115">Um ein Exchange Online Postfach in das Beweissicherungsverfahren einzufügen, muss ihm eine Exchange Online Plan 2-Lizenz zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="37ff6-115">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="37ff6-116">Wenn einem Postfach eine Exchange Online Plan 1-Lizenz zugewiesen ist, müssen Sie ihm eine separate Exchange Online-Archivierungslizenz zuweisen, um ihn in die Warteschleife zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="37ff6-116">If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>
    

## <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="37ff6-117">Aktivieren des Beweissicherungsverfahrens für ein Postfach</span><span class="sxs-lookup"><span data-stu-id="37ff6-117">Place a mailbox on Litigation Hold</span></span>

<span data-ttu-id="37ff6-118">Hier finden Sie die Schritte zum Aufbewahren eines Postfachs für das Beweissicherungsverfahren mithilfe der Exchange-Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="37ff6-118">Here are the steps to place a mailbox on Litigation Hold using the Exchange admin center.</span></span>

1. <span data-ttu-id="37ff6-119">Wechseln Sie [https://outlook.office.com/ecp](https://outlook.office.com/ecp) zu, und melden Sie sich mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="37ff6-119">Go to [https://outlook.office.com/ecp](https://outlook.office.com/ecp) and sign in using your global administrator account.</span></span>

2. <span data-ttu-id="37ff6-120">Klicken Sie im linken Navigationsbereich auf **Empfänger > Postfächer** .</span><span class="sxs-lookup"><span data-stu-id="37ff6-120">Click **Recipients > Mailboxes** in the left navigation pane.</span></span>

3. <span data-ttu-id="37ff6-121">Wählen Sie das Postfach aus, das Sie in das Beweissicherungsverfahren einordnen möchten, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="37ff6-121">Select the mailbox that you want to place on Litigation Hold, and then click **Edit**.</span></span>

4. <span data-ttu-id="37ff6-122">Klicken Sie auf der Eigenschaftenseite des Postfachs auf **Postfachfunktionen**.</span><span class="sxs-lookup"><span data-stu-id="37ff6-122">On the mailbox properties page, click **Mailbox features**.</span></span>
    
5. <span data-ttu-id="37ff6-123">Klicken Sie unter **Beweissicherungsverfahren: Deaktiviert** auf **Aktivieren**, um für das Postfach das Beweissicherungsverfahren zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="37ff6-123">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span>
    
6. <span data-ttu-id="37ff6-124">Geben Sie auf der Seite **Beweissicherungsverfahren** die folgenden optionalen Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="37ff6-124">On the **Litigation hold** page, enter the following optional information:</span></span> 
    
    - <span data-ttu-id="37ff6-125">**Dauer des beweissicherungsverfahrens (Tage)** – verwenden Sie dieses Feld, um einen zeitbasierten Speicher zu erstellen und anzugeben, wie lange Postfachelemente aufbewahrt werden, wenn das Postfach auf das Beweissicherungsverfahren festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="37ff6-125">**Litigation hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold.</span></span> <span data-ttu-id="37ff6-126">Der Zeitraum beginnt mit dem Datum, an dem das Postfachelement empfangen oder erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="37ff6-126">The duration is calculated from the date a mailbox item is received or created.</span></span> <span data-ttu-id="37ff6-127">Wenn die Aufbewahrungsdauer für ein bestimmtes Element abläuft, wird das Element nicht mehr beibehalten.</span><span class="sxs-lookup"><span data-stu-id="37ff6-127">When the hold duration expires for a specific item, that item will no longer be preserved.</span></span> <span data-ttu-id="37ff6-128">Wenn Sie dieses Feld leer lassen, werden Elemente auf unbestimmte Zeit beibehalten oder bis der Haltebereich entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="37ff6-128">If you leave this box blank, items are preserved indefinitely or until the hold is removed.</span></span> <span data-ttu-id="37ff6-129">Geben Sie die Dauer in Tagen an.</span><span class="sxs-lookup"><span data-stu-id="37ff6-129">Use days to specify the duration.</span></span>
    
    - <span data-ttu-id="37ff6-130">**Hinweis** : Verwenden Sie dieses Feld, um dem Benutzer mitzuteilen, dass sein Postfach auf das Beweissicherungsverfahren festgehalten wird.</span><span class="sxs-lookup"><span data-stu-id="37ff6-130">**Note** - Use this box to inform the user their mailbox is on Litigation Hold.</span></span> <span data-ttu-id="37ff6-131">Die Notiz wird auf der Seite Kontoinformationen im Postfach des Benutzers angezeigt, wenn Sie Outlook 2010 oder höher verwenden.</span><span class="sxs-lookup"><span data-stu-id="37ff6-131">The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later.</span></span> <span data-ttu-id="37ff6-132">Um auf diese Seite zuzugreifen, können Benutzer in Outlook auf **Datei** klicken.</span><span class="sxs-lookup"><span data-stu-id="37ff6-132">To access this page, users can click **File** in Outlook.</span></span>
    
    - <span data-ttu-id="37ff6-133">**URL** – verwenden Sie dieses Feld, um den Benutzer zu einer Website zu leiten, um weitere Informationen zur Aufbewahrung von Beweissicherungsverfahren zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="37ff6-133">**URL** - Use this box to direct the user to a website for more information about Litigation Hold.</span></span> <span data-ttu-id="37ff6-134">Diese URL wird auf der Seite Kontoinformationen im Postfach des Benutzers angezeigt, wenn Sie Outlook 2010 oder höher verwenden.</span><span class="sxs-lookup"><span data-stu-id="37ff6-134">This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later.</span></span> <span data-ttu-id="37ff6-135">Um auf diese Seite zuzugreifen, können Benutzer in Outlook auf **Datei** klicken..</span><span class="sxs-lookup"><span data-stu-id="37ff6-135">To access this page, users can click **File** in Outlook..</span></span>

7. <span data-ttu-id="37ff6-136">Klicken Sie auf der Seite **Beweissicherungsverfahren** auf **Speichern** , und klicken Sie dann auf der Seite Postfacheigenschaften auf **Speichern** .</span><span class="sxs-lookup"><span data-stu-id="37ff6-136">Click **Save** on the **Litigation hold** page, and then click **Save** on the mailbox properties page.</span></span>

### <a name="create-a-litigation-hold-using-powershell"></a><span data-ttu-id="37ff6-137">Erstellen eines beweissicherungsverfahrens mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="37ff6-137">Create a Litigation Hold using PowerShell</span></span>

<span data-ttu-id="37ff6-138">Sie können auch ein Beweissicherungsverfahren erstellen, indem Sie den folgenden Befehl in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)ausführen:</span><span class="sxs-lookup"><span data-stu-id="37ff6-138">You can also create a Litigation Hold by running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

<span data-ttu-id="37ff6-139">Der vorherige Befehl behält Elemente auf unbestimmte Zeit bei, da die Aufbewahrungsdauer nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="37ff6-139">The previous command preserves items indefinitely because the hold duration isn't specified.</span></span> <span data-ttu-id="37ff6-140">Zum Erstellen eines zeitbasierten haltebereichs mit dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="37ff6-140">To created a time-based hold, using the following command:</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

<span data-ttu-id="37ff6-141">Weitere Informationen finden Sie unter [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="37ff6-141">For more information, see [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

## <a name="how-does-litigation-hold-work"></a><span data-ttu-id="37ff6-142">Wie funktioniert das Beweissicherungsverfahren?</span><span class="sxs-lookup"><span data-stu-id="37ff6-142">How does Litigation Hold work?</span></span>

<span data-ttu-id="37ff6-143">Beim normalen Löschworkflow wird ein dauerhaft gelöschtes (UMSCHALT+ENTF) oder aus dem Ordner „Gelöschte Elemente" gelöschtes Postfachelement in den Unterordner „Löschvorgänge" des Ordners „Wiederherstellbare Elemente" verschoben.</span><span class="sxs-lookup"><span data-stu-id="37ff6-143">In the normal deleted item workflow, a mailbox item is moved to the Deletions subfolder in the Recoverable Items folder when a user permanently deletes it (Shift + Delete) or deletes it from the Deleted Items folder.</span></span> <span data-ttu-id="37ff6-144">Beim Anwenden einer Löschrichtlinie (hierbei handelt es sich um ein Aufbewahrungstag mit einer konfigurierten Aufbewahrungsaktion) werden Elemente auch nach Ablauf des Aufbewahrungszeitraums in den Unterordner „Löschvorgänge" verschoben.</span><span class="sxs-lookup"><span data-stu-id="37ff6-144">A deletion policy (which is a retention tag configured with a Delete retention action) also moves items to the Deletions subfolder when the retention period expires.</span></span> <span data-ttu-id="37ff6-145">Beim dauerhaften Löschen eines Elements im Ordner „Wiederherstellbare Elemente" durch einen Benutzer oder nach Ablauf der Aufbewahrungsdauer wird das Element in den Unterordner „Endgültige Löschvorgänge" des Ordners „Wiederherstellbare Elemente" verschoben und zum endgültigen Löschen markiert.</span><span class="sxs-lookup"><span data-stu-id="37ff6-145">When a user purges an item in the Recoverable Items folder or when the deleted item retention period expires for an item, it's moved to the Purges subfolder in the Recoverable Items folder and marked for permanent deletion.</span></span> <span data-ttu-id="37ff6-146">Das Element wird beim nächsten Verarbeiten des Postfachs vom Assistenten für verwalteten Ordner aus Exchange dauerhaft gelöscht.</span><span class="sxs-lookup"><span data-stu-id="37ff6-146">It will be purged from Exchange the next time the mailbox is processed by the Managed Folder Assistant (MFA).</span></span>

<span data-ttu-id="37ff6-p108">Ist für das Postfach das Beweissicherungsverfahren aktiviert, werden die Elemente im Unterordner „Endgültige Löschvorgänge" für die für das Beweissicherungsverfahren angegebene Aufbewahrungsdauer aufbewahrt. Die Aufbewahrungsdauer wird anhand des ursprünglichen Datums berechnet,an dem ein Element empfangen oder erstellt wurde und legt fest, wie lange die Elemente im Unterordner „Endgültige Löschvorgänge" aufbewahrt werden. Wenn die Aufbewahrungsdauer für ein Element im Unterordner „Endgültige Löschvorgänge" abläuft, wird das Element zum endgültigen Löschen vorgemerkt und beim nächsten Verarbeiten des Postfachs vom Assistenten für verwalteten Ordner dauerhaft aus Exchange gelöscht. Wenn die dauerhafte Aufbewahrung für ein Postfach aktiviert ist, werden die Elemente nicht aus dem Unterordner „Endgültige Löschvorgänge" gelöscht.</span><span class="sxs-lookup"><span data-stu-id="37ff6-p108">When a mailbox is placed on Litigation Hold, items in the Purges subfolder are preserved for the hold duration specified by the Litigation Hold. The hold duration is calculated from the original date an item was received or created, and defines how long items in the Purges subfolder are held. When the hold duration expires for an item in the Purges subfolder, the item is marked for permanent deletion and will be purged from Exchange the next time the mailbox is processed by the MFA. If an indefinite hold is placed on a mailbox, items will never be purged from the Purges subfolder.</span></span>

<span data-ttu-id="37ff6-151">Die folgende Abbildung zeigt die Unterordner in den Ordnern „Wiederherstellbare Elemente" und den Aufbewahrungsworkflowprozess.</span><span class="sxs-lookup"><span data-stu-id="37ff6-151">The following illustration shows the subfolders in the Recoverable Items folders and the hold workflow process.</span></span>

![Lebenszyklus von Beweissicherungsverfahren](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> <span data-ttu-id="37ff6-153">Wenn ein Haltebereich, der einem eDiscovery-Fall zugeordnet ist, in einem Postfach abgelegt wird, werden gelöschte Elemente aus dem Unterordner "Deletions" in den Unterordner DiscoveryHolds verschoben und bleiben erhalten, bis das Postfach aus der eDiscovery-Aufbewahrungsstelle freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="37ff6-153">If a hold associated with an eDiscovery case is placed on a mailbox, purged items are moved from the Deletions subfolder to the DiscoveryHolds subfolder and are preserved until the mailbox is released from the eDiscovery hold.</span></span>
  
