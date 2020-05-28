---
title: Vergleichen der Möglichkeiten zum Blockieren des Zugriffs
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: Hier erfahren Sie, wie Sie den Zugriff auf Microsoft 365 blockieren, wenn ein Mitarbeiter Ihre Organisation verlässt.
ms.openlocfilehash: b913655065d4c57322aee6dc04e53f7a35cf5760
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399434"
---
# <a name="compare-ways-to-block-access"></a><span data-ttu-id="f4682-103">Vergleichen der Möglichkeiten zum Blockieren des Zugriffs</span><span class="sxs-lookup"><span data-stu-id="f4682-103">Compare ways to block access</span></span>

<span data-ttu-id="f4682-p101">Wenn ein Mitarbeiter Ihre Organisation verlässt, müssen Sie Ihren Zugriff auf Microsoft 365 in gutem Grund oder in schlechtem Rahmen blockieren. Im folgenden finden Sie einige Möglichkeiten, wie Sie dies tun können.</span><span class="sxs-lookup"><span data-stu-id="f4682-p101">When an employee leaves your organization, on good terms or bad, you need to block their access to Microsoft 365. Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="f4682-106">**Möglichkeiten zum Blockieren des Zugriffs**</span><span class="sxs-lookup"><span data-stu-id="f4682-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="f4682-107">**Definition**</span><span class="sxs-lookup"><span data-stu-id="f4682-107">**Definition**</span></span> <br/> |<span data-ttu-id="f4682-108">**Bewährte Methode**</span><span class="sxs-lookup"><span data-stu-id="f4682-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="f4682-109">Anmeldung blockieren</span><span class="sxs-lookup"><span data-stu-id="f4682-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="f4682-p102">Eine Möglichkeit zum Blockieren des Zugriffs auf Microsoft 365 durch einen Benutzer besteht darin, den Anmeldestatus in " **Anmeldung blockiert**" zu ändern. Dadurch wird verhindert, dass Sie sich von ihren Computern und mobilen Geräten bei Microsoft 365 anmelden, obwohl Sie bereits heruntergeladene oder synchronisierte e-Mails und Dokumente anzeigen können. Wenn Sie BlackBerry Enterprise Service verwenden, können Sie auch dort den Zugriff deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f4682-p102">One way to block a user from accessing Microsoft 365 is to change their sign-in status to **Sign-in blocked**. This prevents them from signing into Microsoft 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents. If you're using Blackberry Enterprise Service, you can disable their access there as well.  </span></span><br/> |<span data-ttu-id="f4682-113">Verwenden Sie diese Option, wenn ein Mitarbeiter plant, die Organisation zu verlassen oder langfristig abwesend sein wird.</span><span class="sxs-lookup"><span data-stu-id="f4682-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="f4682-114">Benutzerkennwort zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="f4682-114">Reset user password</span></span>  <br/> |<span data-ttu-id="f4682-p103">Eine andere Möglichkeit, um zu verhindern, dass ein Benutzer auf Microsoft 365 zugreift, besteht darin, sein Kennwort zurückzusetzen. Dadurch wird verhindert, dass Sie Ihr Konto verwenden, obwohl Sie noch zuvor heruntergeladene oder synchronisierte e-Mails und Dokumente anzeigen können. Sie können sich dann als diese anmelden und das Kennwort in eins Ihrer Wahl ändern.</span><span class="sxs-lookup"><span data-stu-id="f4682-p103">Another way to prevent a user from accessing Microsoft 365 is to reset their password. This prevents them from using their account though they can still view previously downloaded or synced email and documents. You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="f4682-118">Verwenden Sie diese Option, wenn ein Mitarbeiter die Organisation unvermittelt und dauerhaft verlässt und Sie sich Sorgen um die Geschäftsdaten machen.</span><span class="sxs-lookup"><span data-stu-id="f4682-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="f4682-119">Alle zugewiesenen Lizenzen entfernen</span><span class="sxs-lookup"><span data-stu-id="f4682-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="f4682-120">Eine weitere Option besteht darin, alle Microsoft 365-Lizenzen zu entfernen, die dem Benutzer zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="f4682-120">Another option is to remove any Microsoft 365 licenses assigned to the user.</span></span> <span data-ttu-id="f4682-121">Damit wird verhindert, dass der Benutzer Anwendungen und Dienste wie die Office-Suite, Office-Apps für das Web, Yammer und SharePoint Online verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4682-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="f4682-122">Der Benutzer kann sich zwar weiterhin anmelden, kann jedoch nicht mehr auf diese Dienste zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f4682-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="f4682-123">Verwenden Sie diese Funktion, wenn Sie der Meinung sind, dass dieser Benutzer nicht mehr auf bestimmte Features in Microsoft 365 zugreifen muss.</span><span class="sxs-lookup"><span data-stu-id="f4682-123">Use when you feel this user no longer needs access to specific features in Microsoft 365.</span></span>  <br/> <br> <span data-ttu-id="f4682-124">**Wichtig:** Wenn Sie eine Lizenz entfernen, wird das Postfach des Benutzers nach 30 Tagen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f4682-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="f4682-125">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="f4682-125">Related articles</span></span>

[<span data-ttu-id="f4682-126">Extern eines Benutzers von Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4682-126">Offboard a user from Microsoft 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="f4682-127">Zurücksetzen des Kennworts eines Benutzers in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4682-127">Reset a user's password in Microsoft 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="f4682-128">Zuweisen von Lizenzen zu Benutzern in Microsoft 365 for Business</span><span class="sxs-lookup"><span data-stu-id="f4682-128">Assign licenses to users in Microsoft 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="f4682-129">Entfernen von Lizenzen von Benutzern in Microsoft 365 for Business</span><span class="sxs-lookup"><span data-stu-id="f4682-129">Remove licenses from users in Microsoft 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

