---
title: Einrichten von Scheduler für Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Einrichten von Scheduler für Microsoft 365.
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286190"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="d0e29-103">Einrichten von Scheduler für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d0e29-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="d0e29-104">Zum Einrichten des Schedulers für Microsoft 365 sind die folgenden Voraussetzungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="d0e29-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="d0e29-105">**Was muss ich tun?**</span><span class="sxs-lookup"><span data-stu-id="d0e29-105">**What do I need?**</span></span> |<span data-ttu-id="d0e29-106">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d0e29-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="d0e29-107">Cortana-Postfach</span><span class="sxs-lookup"><span data-stu-id="d0e29-107">Cortana mailbox</span></span> |<span data-ttu-id="d0e29-108">Mandantenadministratoren müssen ein Postfach als "Cortana"-Postfach festlegen (d. h. cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="d0e29-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="d0e29-109">Exchange Online-Postfach</span><span class="sxs-lookup"><span data-stu-id="d0e29-109">Exchange Online mailbox</span></span> |<span data-ttu-id="d0e29-110">Benutzer müssen über Exchange Online E-Mail und Kalender verfügen</span><span class="sxs-lookup"><span data-stu-id="d0e29-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="d0e29-111">Scheduler-Lizenz</span><span class="sxs-lookup"><span data-stu-id="d0e29-111">Scheduler license</span></span> |<span data-ttu-id="d0e29-112">Informationen zu Lizenzierung und Preisen finden Sie unter [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span><span class="sxs-lookup"><span data-stu-id="d0e29-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="d0e29-113">Erstellen eines Postfachs für Cortana</span><span class="sxs-lookup"><span data-stu-id="d0e29-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="d0e29-114">Ein Exchange in Ihrem Mandanten fungiert als Cortana-Postfach für Ihren Mandanten zum Senden und Empfangen von E-Mails an und von Cortana.</span><span class="sxs-lookup"><span data-stu-id="d0e29-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="d0e29-115">Alle an Cortana gesendeten E-Mails werden basierend auf Ihrer Aufbewahrungsrichtlinie im Cortana-Postfach Ihres Mandanten aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="d0e29-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="d0e29-116">Verwenden Sie Microsoft 365 Admin Center, um ein neues Postfach zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d0e29-116">Use the Microsoft 365 admin center to create a new mailbox.</span></span> <span data-ttu-id="d0e29-117">Es wird eine 30-tägige Aufbewahrungsrichtlinie empfohlen.</span><span class="sxs-lookup"><span data-stu-id="d0e29-117">A 30-day retention policy is recommended.</span></span> <span data-ttu-id="d0e29-118">Verwenden Sie den Namen Cortana in der primären SMTP-Adresse Ihres Postfachs.</span><span class="sxs-lookup"><span data-stu-id="d0e29-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="d0e29-119">Namen wie "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" oder "Cortana.Scheduler@yourdomain.com" werden empfohlen.</span><span class="sxs-lookup"><span data-stu-id="d0e29-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>
- <span data-ttu-id="d0e29-120">Wenden Sie sich an Microsoft (scheduler_m365@microsoft.com), um Ihr Cortana-Postfach zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d0e29-120">Contact Microsoft (scheduler_m365@microsoft.com) to enable your Cortana mailbox.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d0e29-121">Sie müssen sich an Microsoft wenden, um Ihr Cortana-Postfach für die Verwendung des Scheduler-Diensts per E-Mail scheduler_m365@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d0e29-121">You must contact Microsoft to configure your Cortana mailbox to use the Scheduler service by emailing scheduler_m365@microsoft.com.</span></span> <span data-ttu-id="d0e29-122">Die Aktivierung Ihres Cortana-Postfachs kann bis zu zwei Wochen dauern.</span><span class="sxs-lookup"><span data-stu-id="d0e29-122">Enabling your Cortana mailbox may take up to two weeks.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="d0e29-123">Exchange Online-Postfach</span><span class="sxs-lookup"><span data-stu-id="d0e29-123">Exchange Online mailbox</span></span>
<span data-ttu-id="d0e29-124">Scheduler ist ein Add-On für Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d0e29-124">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="d0e29-125">Besprechungsorganisatoren müssen über ein Exchange Online postfach und kalender verfügen, damit Scheduler funktioniert.</span><span class="sxs-lookup"><span data-stu-id="d0e29-125">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="d0e29-126">Exchange-Systemanforderungen</span><span class="sxs-lookup"><span data-stu-id="d0e29-126">Exchange requirements</span></span>

<span data-ttu-id="d0e29-127">Zusätzlich zur Lizenzierung von Scheduler benötigen Sie eine der folgenden Lizenzen:</span><span class="sxs-lookup"><span data-stu-id="d0e29-127">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="d0e29-128">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="d0e29-128">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="d0e29-129">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="d0e29-129">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="d0e29-130">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="d0e29-130">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="d0e29-131">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="d0e29-131">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="d0e29-132">Exchange Online Plan 1- oder Plan 2-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="d0e29-132">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="d0e29-133">**Scheduler für Microsoft 365** ist für Benutzer von Office 365, die von 21Vianet in China betrieben werden, nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d0e29-133">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="d0e29-134">Sie ist auch nicht für Benutzer von Microsoft 365 mit der deutschen Cloud verfügbar, die den Datentreuhänder Deutsche Telekom verwendet.</span><span class="sxs-lookup"><span data-stu-id="d0e29-134">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="d0e29-135">Es wird für Benutzer in Deutschland unterstützt, deren Datenspeicherort sich nicht im deutschen Rechenzentrum befindet.</span><span class="sxs-lookup"><span data-stu-id="d0e29-135">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="d0e29-136">Dieses Feature wird auch nicht für Benutzer der Government Cloud unterstützt (GCC, Consumer, GCC High oder DoD).</span><span class="sxs-lookup"><span data-stu-id="d0e29-136">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
