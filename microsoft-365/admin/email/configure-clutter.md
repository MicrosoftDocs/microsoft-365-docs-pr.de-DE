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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 832276bd-d024-47b6-a80a-a6b884907a5b
description: 'In diesem Artikel erfahren Sie, wie Sie mithilfe von Exchange PowerShell das Feature "clutter" für alle oder bestimmte Benutzer in Ihrer Organisation aktivieren oder deaktivieren. '
ms.openlocfilehash: b71fe20133c78974dc7d1c97a061121eded9f221
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628927"
---
# <a name="configure-clutter-for-your-organization"></a><span data-ttu-id="d76f3-103">Konfigurieren von 'Clutter' für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="d76f3-103">Configure Clutter for your organization</span></span>

> [!TIP]
> <span data-ttu-id="d76f3-104">[Posteingang mit Relevanz](../setup/configure-focused-inbox.md) ersetzt "Clutter".</span><span class="sxs-lookup"><span data-stu-id="d76f3-104">[Focused Inbox](../setup/configure-focused-inbox.md) is going to replace Clutter.</span></span> <span data-ttu-id="d76f3-105">Weitere Informationen: [Update im Posteingang mit Fokus und Pläne für clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span><span class="sxs-lookup"><span data-stu-id="d76f3-105">Learn more: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)</span></span>
  
<span data-ttu-id="d76f3-106">Als Administrator müssen Sie möglicherweise das Feature "clutter" in Microsoft 365 verwalten.</span><span class="sxs-lookup"><span data-stu-id="d76f3-106">As an admin, you may have to manage the Clutter feature in Microsoft 365.</span></span> <span data-ttu-id="d76f3-107">Um das Feature "Clutter" für Benutzer in Ihrer Organisation ein- oder auszuschalten, müssen Sie Exchange PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="d76f3-107">To turn the Clutter feature on/off for users in your organization, you must use Exchange PowerShell.</span></span> <span data-ttu-id="d76f3-108">(Einzelpersonen können das Feature anhand der folgenden Schritte aktivieren/deaktivieren: [Deaktivieren/Aktivieren von Clutter in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).)</span><span class="sxs-lookup"><span data-stu-id="d76f3-108">(Individuals can turn it on/off using these instructions: [Turn off/on Clutter in Outlook](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx).)</span></span> 
  
<span data-ttu-id="d76f3-109">Informationen zur Verwendung von Exchange PowerShell finden Sie unter [Verwenden von PowerShell mit Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) und [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415).</span><span class="sxs-lookup"><span data-stu-id="d76f3-109">Check out [Using PowerShell with Exchange Online](https://go.microsoft.com/fwlink/?LinkID=402831) and [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?LinkID=722415) for details on using Exchange PowerShell.</span></span> <span data-ttu-id="d76f3-110">Sie müssen über ein Konto mit mindestens der Exchange-Dienstadministrator Rolle verfügen und über die Möglichkeit zum Herstellen einer Verbindung mit Exchange Online mit PowerShell verfügen.</span><span class="sxs-lookup"><span data-stu-id="d76f3-110">You need to have an account that has at least the Exchange Service administrator role and the ability to connect to Exchange Online with PowerShell.</span></span> 
  
## <a name="turn-clutter-on-using-exchange-powershell"></a><span data-ttu-id="d76f3-111">Aktivieren von "Clutter" mit Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="d76f3-111">Turn Clutter on using Exchange PowerShell</span></span>

<span data-ttu-id="d76f3-p104">Sie können "Clutter" manuell für ein Postfach aktivieren, indem Sie das Cmdlet [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) ausführen. Sie können auch die Cluttereinstellungen für Postfächer in Ihrer Organisation anzeigen, indem Sie das Cmdlet [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) ausführen.</span><span class="sxs-lookup"><span data-stu-id="d76f3-p104">You can enable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet. You can also view Clutter settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="d76f3-114">Aktivieren von "Clutter" für einen einzigen Benutzer mit Namen Ada Simon</span><span class="sxs-lookup"><span data-stu-id="d76f3-114">Turn on Clutter for a single user named Allie Bellew</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $true`


## <a name="turn-clutter-off-using-exchange-powershell"></a><span data-ttu-id="d76f3-115">Deaktivieren von "Clutter" mit Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="d76f3-115">Turn Clutter off using Exchange PowerShell</span></span>

<span data-ttu-id="d76f3-p105">Sie können "Clutter" manuell für ein Postfach deaktivieren, indem Sie das Cmdlet [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) ausführen. Sie können auch die Einstellungen für **Clutter** für Postfächer in Ihrer Organisation anzeigen, indem Sie das Cmdlet [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) ausführen.</span><span class="sxs-lookup"><span data-stu-id="d76f3-p105">You can disable Clutter manually for a mailbox by running the [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) cmdlet. You can also view **Clutter** settings for mailboxes in your organization by running the [Get-Clutter](https://go.microsoft.com/fwlink/?LinkID=834759) cmdlet.</span></span> 
  
<span data-ttu-id="d76f3-118">Deaktivieren von "Clutter" für einen einzigen Benutzer mit Namen Ada Simon</span><span class="sxs-lookup"><span data-stu-id="d76f3-118">Turn off Clutter for a single user named Allie Bellew:</span></span>
    
`Set-Clutter -Identity "Allie Bellew" -Enable $false`

<span data-ttu-id="d76f3-119">Wenn Sie PowerShell zum Massenerstellen von Benutzern verwenden, müssen Sie [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) für das Postfach eines jeden Benutzers ausführen, um "Clutter" zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="d76f3-119">If you use PowerShell to bulk create your users, then you'll need to run [Set-Clutter](https://go.microsoft.com/fwlink/?LinkID=834446) against each user's mailbox to manage Clutter.</span></span> 
  
## <a name="when-does-the-clutter-onoff-switch-appear-to-users-in-outlook-on-the-web"></a><span data-ttu-id="d76f3-120">Wann wird der Schalter für zum Ein-/Ausschalten von "Clutter" für Benutzer in Outlook im Web angezeigt?</span><span class="sxs-lookup"><span data-stu-id="d76f3-120">When does the Clutter on/off switch appear to users in Outlook on the web?</span></span>
<span data-ttu-id="d76f3-121"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="d76f3-121"><a name="bkmk_onoff"> </a></span></span>

<span data-ttu-id="d76f3-122">Als Administrator können Sie die Übersichtlichkeit mithilfe von Exchange PowerShell wieder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d76f3-122">As an admin, you can re-enable Clutter using Exchange PowerShell.</span></span> <span data-ttu-id="d76f3-123">Wenn Sie dies tun, wird der Posteingang mit Relevanz deaktiviert und "Clutter" wieder aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d76f3-123">Once this is done, Focused Inbox will be turned off and Clutter will be active again.</span></span> 
  
 <span data-ttu-id="d76f3-124">**Wenn Sie Outlook im Internet mit einem Microsoft 365 Business Premium-Abonnement verwenden:**</span><span class="sxs-lookup"><span data-stu-id="d76f3-124">**If you're using Outlook on the web with a Microsoft 365 Business Premium subscription:**</span></span>
  
- <span data-ttu-id="d76f3-125">Wenn für den Benutzer aktuell "Clutter" aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="d76f3-125">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="d76f3-126">Die "Clutter"-Einstellungen werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d76f3-126">Clutter settings appear</span></span>
    
- <span data-ttu-id="d76f3-127">Wenn für den Benutzer aktuell "Posteingang mit Relevanz" aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="d76f3-127">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="d76f3-128">Die "Clutter"-Einstellungen werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d76f3-128">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="d76f3-129">Wenn weder "Clutter" noch "Posteingang mit Relevanz" aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="d76f3-129">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="d76f3-130">In den Mails-Einstellungen des Benutzers werden "Clutter" und auch "Posteingang mit Relevanz" als Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d76f3-130">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
 <span data-ttu-id="d76f3-131">**Bei Verwendung von Outlook.com:**</span><span class="sxs-lookup"><span data-stu-id="d76f3-131">**If you're using Outlook.com:**</span></span>
  
- <span data-ttu-id="d76f3-132">Wenn für den Benutzer aktuell "Clutter" aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="d76f3-132">If user currently has Clutter enabled:</span></span> 
    
  - <span data-ttu-id="d76f3-133">Die "Clutter"-Einstellungen werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d76f3-133">Clutter settings appear</span></span>
    
- <span data-ttu-id="d76f3-134">Wenn für den Benutzer aktuell "Posteingang mit Relevanz" aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="d76f3-134">If user currently has Focused Inbox enabled:</span></span> 
    
  - <span data-ttu-id="d76f3-135">Die "Clutter"-Einstellungen werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d76f3-135">Clutter settings will not appear</span></span>
    
- <span data-ttu-id="d76f3-136">Wenn weder "Clutter" noch "Posteingang mit Relevanz" aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="d76f3-136">If neither Clutter or Focused Inbox is enabled:</span></span> 
    
  - <span data-ttu-id="d76f3-137">In den Mails-Einstellungen des Benutzers werden "Clutter" und auch "Posteingang mit Relevanz" als Optionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d76f3-137">Both Clutter and Focused Inbox appear as options in the user's Mail Settings</span></span>
    
- <span data-ttu-id="d76f3-138">Wenn der Benutzer den Posteingang mit Relevanz in der Vergangenheit aktiviert hat:</span><span class="sxs-lookup"><span data-stu-id="d76f3-138">If user enabled Focused Inbox at some point in the past:</span></span>
    
  - <span data-ttu-id="d76f3-139">Die "Clutter"-Einstellungen werden nie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d76f3-139">Clutter settings will never appear</span></span>
    
    <span data-ttu-id="d76f3-140">Andernfalls:</span><span class="sxs-lookup"><span data-stu-id="d76f3-140">Otherwise,</span></span> 
    
  - <span data-ttu-id="d76f3-141">Die "Clutter"-Einstellungen werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d76f3-141">Clutter settings will appear</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="d76f3-142">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="d76f3-142">Related articles</span></span>
<span data-ttu-id="d76f3-143"><a name="bkmk_onoff"> </a></span><span class="sxs-lookup"><span data-stu-id="d76f3-143"><a name="bkmk_onoff"> </a></span></span>

[<span data-ttu-id="d76f3-144">Verwenden der Funktion „Clutter" zum Sortieren von Nachrichten mit niedriger Priorität in Outlook</span><span class="sxs-lookup"><span data-stu-id="d76f3-144">Use Clutter to sort low priority messages in Outlook</span></span>](https://support.office.com/article/7755ebf5-4585-469b-b1ab-8b12425c6b6b.aspx)
    
[<span data-ttu-id="d76f3-145">Verwenden von clutter zum Sortieren von Nachrichten mit niedriger Priorität in OWA</span><span class="sxs-lookup"><span data-stu-id="d76f3-145">Use Clutter to sort low priority messages in OWA</span></span>](https://support.office.com/article/fe4d64ca-bf73-48f1-91b4-9a659e008bce.aspx)
    
[<span data-ttu-id="d76f3-146">Deaktivieren von "Clutter" in Outlook</span><span class="sxs-lookup"><span data-stu-id="d76f3-146">Turn off Clutter in Outlook</span></span>](https://support.office.com/article/a9c72a77-1bc4-40e6-ba6d-103c1d1aba4c.aspx)
    

