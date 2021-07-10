---
title: Einrichten des Schedulers für Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Einrichten des Schedulers für Microsoft 365.
ms.openlocfilehash: 924b25e3d921f402c97632f7475ed5beea98d5c7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362546"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="9b316-103">Einrichten des Planers für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9b316-103">Setting up Scheduler for Microsoft 365</span></span>


<span data-ttu-id="9b316-104">Zum Einrichten des Schedulers für Microsoft 365 sind die folgenden Voraussetzungen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="9b316-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

| <span data-ttu-id="9b316-105">Was benöte ich?</span><span class="sxs-lookup"><span data-stu-id="9b316-105">What do I need?</span></span> | <span data-ttu-id="9b316-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b316-106">Description</span></span> |
|-------------------|-------------|
|<span data-ttu-id="9b316-107">Cortana Postfach</span><span class="sxs-lookup"><span data-stu-id="9b316-107">Cortana mailbox</span></span> |<span data-ttu-id="9b316-108">Mandantenadministratoren müssen ein Postfach so festlegen, dass es als "Cortana"-Postfach (d. cortana@yourdomain.com) dient.</span><span class="sxs-lookup"><span data-stu-id="9b316-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="9b316-109">Exchange Online-Postfach</span><span class="sxs-lookup"><span data-stu-id="9b316-109">Exchange Online mailbox</span></span> |<span data-ttu-id="9b316-110">Benutzer müssen über eine Exchange Online E-Mail und einen Kalender verfügen</span><span class="sxs-lookup"><span data-stu-id="9b316-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="9b316-111">Scheduler-Lizenz</span><span class="sxs-lookup"><span data-stu-id="9b316-111">Scheduler license</span></span> |<span data-ttu-id="9b316-112">Informationen zu Lizenzierung und Preisen finden Sie unter [Scheduler für Microsoft 365.](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing)</span><span class="sxs-lookup"><span data-stu-id="9b316-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="9b316-113">Erstellen eines Postfachs für Cortana</span><span class="sxs-lookup"><span data-stu-id="9b316-113">Create a mailbox for Cortana</span></span>

<span data-ttu-id="9b316-114">Ein Exchange Postfach in Ihrem Mandanten fungiert als Cortana Postfach, mit dem Ihr Mandant E-Mails an und von Cortana senden und empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="9b316-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="9b316-115">Alle an Cortana gesendeten E-Mails werden basierend auf Ihrer Aufbewahrungsrichtlinie im Cortana Postfach Ihres Mandanten aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="9b316-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="9b316-116">Verwenden Sie die Microsoft 365 Admin Center, um ein Benutzerpostfach zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9b316-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="9b316-117">Es wird eine Aufbewahrungsrichtlinie für 30 Tage empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9b316-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="9b316-118">Verwenden Sie den Namen Cortana in der primären SMTP-Adresse Ihres Postfachs.</span><span class="sxs-lookup"><span data-stu-id="9b316-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="9b316-119">Namen wie "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" oder "Cortana". Scheduler@yourdomain.com' werden empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9b316-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="9b316-120">Festlegen des Postfachs als Planer-Assistent</span><span class="sxs-lookup"><span data-stu-id="9b316-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="9b316-121">Nachdem ein eindeutiges Postfach für Cortana Scheduler erstellt wurde, müssen Sie das Postfach formell Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9b316-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="9b316-122">Nachdem Sie das Cortana Scheduler-Postfach festgelegt haben, steht es zur Verfügung, um Besprechungen im Namen Ihrer Benutzer zu planen.</span><span class="sxs-lookup"><span data-stu-id="9b316-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="9b316-123">Um das Cortana Scheduler-Postfach festzulegen, muss ein autorisierter Administrator einen einzeiligen PowerShell-Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="9b316-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="9b316-124">Verbinden zum Microsoft 365 Remote-PowerShell-Ausführungsspeicherplatz für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="9b316-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>

2. <span data-ttu-id="9b316-125">Führen Sie das folgende PowerShell-Skript aus, um das Postfach für Scheduler festzulegen:</span><span class="sxs-lookup"><span data-stu-id="9b316-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    <span data-ttu-id="9b316-126">Nachdem Sie diesen Befehl "festlegen" im Cortana Scheduler-Postfach ausgeführt haben, wird für das Postfach eine neue "PersistedCapability" festgelegt, um zu beachten, dass dieses Postfach "SchedulerAssistant" ist.</span><span class="sxs-lookup"><span data-stu-id="9b316-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="9b316-127">Führen Sie die folgenden Schritte aus, um Ihre Organisation mit PowerShell zu verbinden, wenn Sie dies zuvor noch nicht getan haben: [Verbinden Microsoft 365 mit PowerShell.](../enterprise/connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="9b316-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="9b316-128">Führen Sie die Get-Funktion aus, um zu ermitteln, welches Postfach in Ihrer Organisation derzeit als Cortana Scheduler-Assistent festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="9b316-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> <span data-ttu-id="9b316-129">Es kann bis zu zwei Stunden dauern, bis das Scheduler-Postfach die vollständige Bereitstellung abgeschlossen hat, um die SchedulerAssistant-Funktion festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9b316-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="9b316-130">Exchange Online-Postfach</span><span class="sxs-lookup"><span data-stu-id="9b316-130">Exchange Online mailbox</span></span>
<span data-ttu-id="9b316-131">Eine Scheduler-Lizenz ist ein Add-On für Microsoft 365, mit dem der Besprechungsorganisator seine Besprechungsplanungsaufgaben an den Planer-Assistenten delegieren kann.</span><span class="sxs-lookup"><span data-stu-id="9b316-131">A Scheduler license is an add-on to Microsoft 365, that enables the meeting organizer to delegate their meeting scheduling tasks to their Scheduler assistant.</span></span> <span data-ttu-id="9b316-132">Damit der Planer funktioniert, in der Regel über Microsoft 365 Lizenz, benötigen Besprechungsorganisatoren die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="9b316-132">For the Scheduler to work, typically through Microsoft 365 license, meeting organizers require the following components:</span></span>

- <span data-ttu-id="9b316-133">Ein Postfach, das als Postfach des Planer-Assistenten festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="9b316-133">A mailbox designated as Scheduler assistant mailbox</span></span>
- <span data-ttu-id="9b316-134">Scheduler-Lizenz</span><span class="sxs-lookup"><span data-stu-id="9b316-134">Scheduler license</span></span>
- <span data-ttu-id="9b316-135">Exchange Online Postfach und Kalender</span><span class="sxs-lookup"><span data-stu-id="9b316-135">Exchange Online mailbox and calendar</span></span>

<span data-ttu-id="9b316-136">Die Besprechungsteilnehmer benötigen keine Scheduler- oder Microsoft 365-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="9b316-136">The meeting attendees do not require Scheduler or Microsoft 365 license.</span></span>

## <a name="scheduler-end-user-license-requirements"></a><span data-ttu-id="9b316-137">Lizenzanforderungen für Scheduler-Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="9b316-137">Scheduler end-user license requirements</span></span>

<span data-ttu-id="9b316-138">Eine Scheduler-Lizenz erfordert eine der folgenden Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="9b316-138">A Scheduler license requires one of the following licenses:</span></span>

- <span data-ttu-id="9b316-139">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="9b316-139">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="9b316-140">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="9b316-140">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="9b316-141">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="9b316-141">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="9b316-142">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="9b316-142">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="9b316-143">Exchange Online Plan 1- oder Plan 2-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="9b316-143">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]

> <span data-ttu-id="9b316-144">Scheduler für Microsoft 365 ist nur in weltweiten mehrinstanzenfähigen Umgebungen in Englisch verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9b316-144">Scheduler for Microsoft 365 is available in worldwide multi-tenant environments in English only.</span></span> <span data-ttu-id="9b316-145">**Der Scheduler für Microsoft 365** ist für Benutzer von:</span><span class="sxs-lookup"><span data-stu-id="9b316-145">**Scheduler for Microsoft 365** isn't available to users of:</span></span>

- <span data-ttu-id="9b316-146">Microsoft 365 betrieben von 21Vianet in China</span><span class="sxs-lookup"><span data-stu-id="9b316-146">Microsoft 365 operated by 21Vianet in China</span></span>
- <span data-ttu-id="9b316-147">Microsoft 365 mit der deutschen Cloud, die den Datentreuhänder Deutsche Telekom verwendet</span><span class="sxs-lookup"><span data-stu-id="9b316-147">Microsoft 365 with German cloud that uses the data trustee German Telekom</span></span>
- <span data-ttu-id="9b316-148">Government Cloud, einschließlich GCC, Consumer, GCC High oder DoD</span><span class="sxs-lookup"><span data-stu-id="9b316-148">Government cloud including GCC, Consumer, GCC High, or DoD</span></span>

<span data-ttu-id="9b316-149">Der Scheduler unterstützt Benutzer in Deutschland, deren Datenspeicherort sich nicht im deutschen Rechenzentrum befindet.</span><span class="sxs-lookup"><span data-stu-id="9b316-149">Scheduler does support users in Germany whose data location is not in the German datacenter.</span></span>
