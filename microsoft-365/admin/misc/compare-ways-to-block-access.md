---
title: Vergleich der Möglichkeiten zum Blockieren des Zugriffs auf Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5785d21d-1abd-4571-a04a-8cc5a65ca9b5
ROBOTS: NOINDEX
description: Erfahren Sie, wie Sie den Zugriff auf Office 365 blockieren können, wenn ein Mitarbeiter Ihre Organisation verlässt.
ms.openlocfilehash: 3aafef37a43747557ef9a3fcda8ffe0fe3713717
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254327"
---
# <a name="compare-ways-to-block-access-to-office-365"></a><span data-ttu-id="7ff9b-103">Vergleich der Möglichkeiten zum Blockieren des Zugriffs auf Office 365</span><span class="sxs-lookup"><span data-stu-id="7ff9b-103">Compare ways to block access to Office 365</span></span>

<span data-ttu-id="7ff9b-p101">Wenn ein Mitarbeiter Ihre Organisation verlässt, sei es im Guten oder im Bösen, müssen Sie dessen Zugriff auf Office 365 sperren. Hier einige Möglichkeiten, wie Sie vorgehen können.</span><span class="sxs-lookup"><span data-stu-id="7ff9b-p101">When an employee leaves your organization, on good terms or bad, you need to block their access to Office 365. Here are a few ways you can do that.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="7ff9b-106">**Möglichkeiten zum Blockieren des Zugriffs**</span><span class="sxs-lookup"><span data-stu-id="7ff9b-106">**Way to block access**</span></span> <br/> |<span data-ttu-id="7ff9b-107">**Definition**</span><span class="sxs-lookup"><span data-stu-id="7ff9b-107">**Definition**</span></span> <br/> |<span data-ttu-id="7ff9b-108">**Bewährte Methode**</span><span class="sxs-lookup"><span data-stu-id="7ff9b-108">**Best practice**</span></span> <br/> |
|<span data-ttu-id="7ff9b-109">Anmeldung blockieren</span><span class="sxs-lookup"><span data-stu-id="7ff9b-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="7ff9b-p102">Eine Möglichkeit zum Sperren des Zugriffs eines Benutzers auf Office 365 besteht darin, den Anmeldestatus auf **Benutzer mit blockierter Anmeldung** festzulegen. Damit wird verhindert, dass sich der Benutzer von seinem Computer und von mobilen Geräten bei Office 365 anmeldet. Er kann jedoch weiterhin zuvor heruntergeladene oder synchronisierte E-Mails und Dokumente anzeigen. Wenn Sie Blackberry Enterprise Service verwenden, können Sie den Zugriff hierauf ebenfalls deaktivieren.  </span><span class="sxs-lookup"><span data-stu-id="7ff9b-p102">One way to block a user from accessing Office 365 is to change their sign-in status to **Sign-in blocked**. This prevents them from signing into Office 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents. If you're using Blackberry Enterprise Service, you can disable their access there as well.  </span></span><br/> |<span data-ttu-id="7ff9b-113">Verwenden Sie diese Option, wenn ein Mitarbeiter plant, die Organisation zu verlassen oder langfristig abwesend sein wird.</span><span class="sxs-lookup"><span data-stu-id="7ff9b-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="7ff9b-114">Benutzerkennwort zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="7ff9b-114">Reset user password</span></span>  <br/> |<span data-ttu-id="7ff9b-p103">Eine weitere Möglichkeit, um zu verhindern, dass ein Benutzer auf Office 365 zugreift, besteht darin, das Kennwort zurückzusetzen. Damit wird verhindert, dass das Konto genutzt wird, der Benutzer kann jedoch weiterhin heruntergeladene oder synchronisierte E-Mails und Dokumente anzeigen. Sie können sich unter dem Namen des Benutzers anmelden und das Kennwort in ein von Ihnen gewähltes ändern.</span><span class="sxs-lookup"><span data-stu-id="7ff9b-p103">Another way to prevent a user from accessing Office 365 is to reset their password. This prevents them from using their account though they can still view previously downloaded or synced email and documents. You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="7ff9b-118">Verwenden Sie diese Option, wenn ein Mitarbeiter die Organisation unvermittelt und dauerhaft verlässt und Sie sich Sorgen um die Geschäftsdaten machen.</span><span class="sxs-lookup"><span data-stu-id="7ff9b-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="7ff9b-119">Alle zugewiesenen Lizenzen entfernen</span><span class="sxs-lookup"><span data-stu-id="7ff9b-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="7ff9b-120">Eine weitere Möglichkeit besteht darin, alle Office 365-Lizenzen zu entfernen, die dem Benutzer zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="7ff9b-120">Another option is to remove any Office 365 licenses assigned to the user.</span></span> <span data-ttu-id="7ff9b-121">Damit wird verhindert, dass der Benutzer Anwendungen und Dienste wie die Office-Suite, Office-Apps für das Web, Yammer und SharePoint Online verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ff9b-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="7ff9b-122">Der Benutzer kann sich zwar weiterhin anmelden, kann jedoch nicht mehr auf diese Dienste zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7ff9b-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="7ff9b-123">Verwenden Sie diese Option, wenn der Benutzer auf bestimmte Features in Office 365 nicht mehr zugreifen muss.</span><span class="sxs-lookup"><span data-stu-id="7ff9b-123">Use when you feel this user no longer needs access to specific features in Office 365.</span></span>  <br/> <br> <span data-ttu-id="7ff9b-124">**Wichtig:** Wenn Sie eine Lizenz entfernen, wird das Postfach des Benutzers nach 30 Tagen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="7ff9b-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="7ff9b-125">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="7ff9b-125">Related articles</span></span>

[<span data-ttu-id="7ff9b-126">Ausschließen eines Benutzers aus Office 365</span><span class="sxs-lookup"><span data-stu-id="7ff9b-126">Offboard a user from Office 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="7ff9b-127">Zurücksetzen eines Benutzerkennworts in Office 365</span><span class="sxs-lookup"><span data-stu-id="7ff9b-127">Reset a user's password in Office 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="7ff9b-128">Zuweisen von Lizenzen zu Benutzern in Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="7ff9b-128">Assign licenses to users in Office 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="7ff9b-129">Entfernen von Lizenzen für Benutzer in Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="7ff9b-129">Remove licenses from users in Office 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

