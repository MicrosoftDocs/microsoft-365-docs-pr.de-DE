---
title: Konfigurieren von 'Clutter' für Ihre Organisation
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'Erfahren Sie, wie Sie das Clutter-Feature für alle oder bestimmte Benutzer in Ihrer Organisation mithilfe von powerShell Exchange aktivieren oder deaktivieren. '
ms.openlocfilehash: ac68893bc0aeea5ab214698c54524921e2b1921d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915902"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="a0862-103">Konfigurieren von 'Clutter' für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="a0862-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="a0862-104">[Posteingang mit Relevanz](../setup/configure-focused-inbox.md) ersetzt "Clutter".</span><span class="sxs-lookup"><span data-stu-id="a0862-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="a0862-105">Weitere Informationen: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="a0862-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="a0862-106">Als Administrator müssen Sie möglicherweise das Clutter-Feature in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a0862-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="a0862-107">Um das Feature "Clutter" für Benutzer in Ihrer Organisation ein- oder auszuschalten, müssen Sie Exchange PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="a0862-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="a0862-108">(Einzelpersonen können dies mithilfe der folgenden Anweisungen [aktivieren/deaktivieren: Deaktivieren/Aktivieren](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)von Clutter in Outlook .</span><span class="sxs-lookup"><span data-stu-id="a0862-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c).</span></span>
  
<span data-ttu-id="a0862-109">Informationen zur Verwendung von Exchange PowerShell finden Sie unter [Verwenden von PowerShell mit Exchange Online](/powershell/exchange/exchange-online-powershell) und [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a0862-109">Check out [Using PowerShell with Exchange Online](/powershell/exchange/exchange-online-powershell) and [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="a0862-110">Sie benötigen ein Konto, das mindestens die Rolle Exchange Dienstadministrators und die Möglichkeit hat, eine Verbindung mit Exchange Online PowerShell herzustellen.</span><span class="sxs-lookup"><span data-stu-id="a0862-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="a0862-111">Aktivieren von "Clutter" mit Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0862-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="a0862-p104">Sie können "Clutter" manuell für ein Postfach aktivieren, indem Sie das Cmdlet [Set-Clutter](/powershell/module/exchange/set-clutter) ausführen. Sie können auch die Cluttereinstellungen für Postfächer in Ihrer Organisation anzeigen, indem Sie das Cmdlet [Get-Clutter](/powershell/module/exchange/get-clutter) ausführen.</span><span class="sxs-lookup"><span data-stu-id="a0862-p104">You can enable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet. You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="a0862-114">Aktivieren von "Clutter" für einen einzigen Benutzer mit Namen Ada Simon</span><span class="sxs-lookup"><span data-stu-id="a0862-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="a0862-115">Deaktivieren von "Clutter" mit Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0862-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="a0862-p105">Sie können "Clutter" manuell für ein Postfach deaktivieren, indem Sie das Cmdlet [Set-Clutter](/powershell/module/exchange/set-clutter) ausführen. Sie können auch die Einstellungen für **Clutter** für Postfächer in Ihrer Organisation anzeigen, indem Sie das Cmdlet [Get-Clutter](/powershell/module/exchange/get-clutter) ausführen.</span><span class="sxs-lookup"><span data-stu-id="a0862-p105">You can disable Clutter manually for a mailbox by running the [Set-Clutter](/powershell/module/exchange/set-clutter) cmdlet. You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](/powershell/module/exchange/get-clutter) cmdlet.</span></span> 
  
<span data-ttu-id="a0862-118">Deaktivieren von "Clutter" für einen einzigen Benutzer mit Namen Ada Simon</span><span class="sxs-lookup"><span data-stu-id="a0862-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="a0862-119">Wenn Sie PowerShell zum Massenerstellen von Benutzern verwenden, müssen Sie [Set-Clutter](/powershell/module/exchange/set-clutter) für das Postfach eines jeden Benutzers ausführen, um "Clutter" zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="a0862-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](/powershell/module/exchange/set-clutter) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="a0862-120">Wann wird der Schalter für zum Ein-/Ausschalten von "Clutter" für Benutzer in Outlook im Web angezeigt?</span><span class="sxs-lookup"><span data-stu-id="a0862-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="a0862-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="a0862-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="a0862-122">Als Administrator können Sie "Clutter" mithilfe Exchange PowerShell erneut aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a0862-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="a0862-123">Wenn Sie dies tun, wird der Posteingang mit Relevanz deaktiviert und "Clutter" wieder aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a0862-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="a0862-124">**Wenn Sie eine Outlook im Web mit einem Microsoft 365 Business Premium verwenden:**</span><span class="sxs-lookup"><span data-stu-id="a0862-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="a0862-125">Wenn für den Benutzer aktuell "Clutter" aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="a0862-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="a0862-126">Die "Clutter"-Einstellungen werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0862-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="a0862-127">Wenn für den Benutzer aktuell "Posteingang mit Relevanz" aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="a0862-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="a0862-128">Die "Clutter"-Einstellungen werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0862-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="a0862-129">Wenn weder "Clutter" noch "Posteingang mit Relevanz" aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="a0862-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="a0862-130">In den Mails-Einstellungen des Benutzers werden "Clutter" und auch "Posteingang mit Relevanz" als Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0862-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="a0862-131">**Bei Verwendung von Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="a0862-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="a0862-132">Wenn für den Benutzer aktuell "Clutter" aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="a0862-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="a0862-133">Die "Clutter"-Einstellungen werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0862-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="a0862-134">Wenn für den Benutzer aktuell "Posteingang mit Relevanz" aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="a0862-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="a0862-135">Die "Clutter"-Einstellungen werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0862-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="a0862-136">Wenn weder "Clutter" noch "Posteingang mit Relevanz" aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="a0862-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="a0862-137">In den Mails-Einstellungen des Benutzers werden "Clutter" und auch "Posteingang mit Relevanz" als Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0862-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="a0862-138">Wenn der Benutzer den Posteingang mit Relevanz in der Vergangenheit aktiviert hat:</span><span class="sxs-lookup"><span data-stu-id="a0862-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="a0862-139">Die "Clutter"-Einstellungen werden nie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0862-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="a0862-140">Andernfalls:</span><span class="sxs-lookup"><span data-stu-id="a0862-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="a0862-141">Die "Clutter"-Einstellungen werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0862-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="a0862-142">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="a0862-142">Related articles</span></span>
<span data-ttu-id="a0862-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="a0862-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="a0862-144">Verwenden der Funktion „Clutter" zum Sortieren von Nachrichten mit niedriger Priorität in Outlook</span><span class="sxs-lookup"><span data-stu-id="a0862-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.microsoft.com/office/7b50c5db-7704-4e55-8a1b-dfc7bf1eafa0)
    
[<span data-ttu-id="a0862-145">Sortieren von Nachrichten mit niedriger Priorität in OWA mithilfe von "Clutter"</span><span class="sxs-lookup"><span data-stu-id="a0862-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.microsoft.com/office/fe4d64ca-bf73-48f1-91b4-9a659e008bce)
    
[<span data-ttu-id="a0862-146">Deaktivieren von "Clutter" in Outlook</span><span class="sxs-lookup"><span data-stu-id="a0862-146">Turn off Clutter in Outlook</span></span>](https://support.microsoft.com/office/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c)
