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
ms.openlocfilehash: c17cdbbf71359a2725a3b0a145cba5feffd7c853
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809191"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="2efe5-103">Einrichten des Schedulers für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2efe5-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="2efe5-104">Zum Einrichten des Schedulers für Microsoft 365 sind die folgenden Voraussetzungen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="2efe5-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="2efe5-105">**Was benöte ich?**</span><span class="sxs-lookup"><span data-stu-id="2efe5-105">**What do I need?**</span></span> |<span data-ttu-id="2efe5-106">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2efe5-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="2efe5-107">Cortana-Postfach</span><span class="sxs-lookup"><span data-stu-id="2efe5-107">Cortana mailbox</span></span> |<span data-ttu-id="2efe5-108">Mandantenadministratoren müssen ein Postfach festlegen, das als "Cortana"-Postfach (d. cortana@yourdomain.com) dient.</span><span class="sxs-lookup"><span data-stu-id="2efe5-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="2efe5-109">Exchange Online-Postfach</span><span class="sxs-lookup"><span data-stu-id="2efe5-109">Exchange Online mailbox</span></span> |<span data-ttu-id="2efe5-110">Benutzer müssen über eine Exchange Online E-Mail und einen Kalender verfügen</span><span class="sxs-lookup"><span data-stu-id="2efe5-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="2efe5-111">Scheduler-Lizenz</span><span class="sxs-lookup"><span data-stu-id="2efe5-111">Scheduler license</span></span> |<span data-ttu-id="2efe5-112">Informationen zu Lizenzierung und Preisen finden Sie unter [Scheduler für Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span><span class="sxs-lookup"><span data-stu-id="2efe5-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="2efe5-113">Erstellen eines Postfachs für Cortana</span><span class="sxs-lookup"><span data-stu-id="2efe5-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="2efe5-114">Ein Exchange Postfach in Ihrem Mandanten fungiert als Cortana-Postfach für Ihren Mandanten zum Senden und Empfangen von E-Mails an und von Cortana.</span><span class="sxs-lookup"><span data-stu-id="2efe5-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="2efe5-115">Alle an Cortana gesendeten E-Mails werden basierend auf Ihrer Aufbewahrungsrichtlinie im Cortana-Postfach Ihres Mandanten aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="2efe5-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="2efe5-116">Verwenden Sie das Microsoft 365 Admin Center, um ein Benutzerpostfach zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2efe5-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="2efe5-117">Es wird eine Aufbewahrungsrichtlinie für 30 Tage empfohlen.</span><span class="sxs-lookup"><span data-stu-id="2efe5-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="2efe5-118">Verwenden Sie den Namen Cortana in der primären SMTP-Adresse Ihres Postfachs.</span><span class="sxs-lookup"><span data-stu-id="2efe5-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="2efe5-119">Es werden Namen wie "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" oder "Cortana.Scheduler@yourdomain.com" empfohlen.</span><span class="sxs-lookup"><span data-stu-id="2efe5-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="2efe5-120">Festlegen des Postfachs als Planer-Assistent</span><span class="sxs-lookup"><span data-stu-id="2efe5-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="2efe5-121">Nachdem ein eindeutiges Postfach für Cortana Scheduler erstellt wurde, müssen Sie das Postfach so festlegen, dass es formell Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2efe5-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="2efe5-122">Nachdem Sie das Cortana Scheduler-Postfach festgelegt haben, steht es zur Verfügung, um Besprechungen im Namen Ihrer Benutzer zu planen.</span><span class="sxs-lookup"><span data-stu-id="2efe5-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="2efe5-123">Um das Cortana Scheduler-Postfach festzulegen, muss ein autorisierter Administrator einen einzeiligen PowerShell-Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="2efe5-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="2efe5-124">Verbinden zum Microsoft 365 Remote-PowerShell-Ausführungsspeicherplatz für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="2efe5-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>
2. <span data-ttu-id="2efe5-125">Führen Sie das folgende PowerShell-Skript aus, um das Postfach für Scheduler festzulegen:</span><span class="sxs-lookup"><span data-stu-id="2efe5-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

<span data-ttu-id="2efe5-126">Nachdem Sie diesen "set"-Befehl im Cortana Scheduler-Postfach ausgeführt haben, wird für das Postfach eine neue "PersistedCapability" festgelegt, um zu beachten, dass dieses Postfach "SchedulerAssistant" ist.</span><span class="sxs-lookup"><span data-stu-id="2efe5-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="2efe5-127">Führen Sie die folgenden Schritte aus, um Ihre Organisation mit PowerShell zu verbinden, wenn Sie dies zuvor noch nicht getan haben: [Verbinden zum Microsoft 365 mit PowerShell – Microsoft 365 Enterprise | Microsoft-Dokumente](../enterprise/connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="2efe5-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell - Microsoft 365 Enterprise | Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)</span></span>

<span data-ttu-id="2efe5-128">Um zu ermitteln, welches Postfach in Ihrer Organisation derzeit als Cortana Scheduler-Assistent festgelegt ist, führen Sie die Get-Funktion aus:</span><span class="sxs-lookup"><span data-stu-id="2efe5-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>
 
```powershell

Get-mailbox -Organization contoso.com | where {($_.PersistedCapabilities -like "SchedulerAssistant")}

```

> [!IMPORTANT]
> <span data-ttu-id="2efe5-129">Es kann bis zu zwei Stunden dauern, bis das Scheduler-Postfach die vollständige Bereitstellung abgeschlossen hat, um die SchedulerAssistant-Funktion festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2efe5-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="2efe5-130">Exchange Online-Postfach</span><span class="sxs-lookup"><span data-stu-id="2efe5-130">Exchange Online mailbox</span></span>
<span data-ttu-id="2efe5-131">Scheduler ist ein Add-On für Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2efe5-131">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="2efe5-132">Besprechungsorganisatoren müssen über ein Exchange Online Postfach und einen Kalender verfügen, damit scheduler funktioniert.</span><span class="sxs-lookup"><span data-stu-id="2efe5-132">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="2efe5-133">Exchange-Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="2efe5-133">Exchange requirements</span></span>

<span data-ttu-id="2efe5-134">Zusätzlich zum Lizenzierungsplaner benötigen Sie eine der folgenden Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="2efe5-134">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="2efe5-135">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="2efe5-135">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="2efe5-136">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="2efe5-136">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="2efe5-137">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="2efe5-137">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="2efe5-138">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="2efe5-138">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="2efe5-139">Exchange Online Plan 1- oder Plan 2-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="2efe5-139">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="2efe5-140">**Der Planer für Microsoft 365** ist für Benutzer von Office 365, betrieben von 21Vianet in China, nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2efe5-140">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="2efe5-141">Es steht auch nicht für Benutzer von Microsoft 365 mit der deutschen Cloud zur Verfügung, die den Datentreuhänder Deutsche Telekom verwendet.</span><span class="sxs-lookup"><span data-stu-id="2efe5-141">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="2efe5-142">Es wird für Benutzer in Deutschland unterstützt, deren Datenspeicherort sich nicht im deutschen Rechenzentrum befindet.</span><span class="sxs-lookup"><span data-stu-id="2efe5-142">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="2efe5-143">Dieses Feature wird auch nicht für Benutzer der Government Cloud unterstützt (GCC, Consumer, GCC High oder DoD).</span><span class="sxs-lookup"><span data-stu-id="2efe5-143">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
