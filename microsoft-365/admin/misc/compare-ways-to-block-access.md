---
title: Vergleichen von Möglichkeiten zum Blockieren des Zugriffs
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
description: Erfahren Sie, wie Sie den Zugriff auf Microsoft 365 blockieren, wenn ein Mitarbeiter Ihre Organisation verlässt.
ms.openlocfilehash: 0c4b210f9802995a23acbf64241997b8924c00c0
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924767"
---
# <a name="compare-ways-to-block-access"></a><span data-ttu-id="1d719-103">Vergleichen von Möglichkeiten zum Blockieren des Zugriffs</span><span class="sxs-lookup"><span data-stu-id="1d719-103">Compare ways to block access</span></span>

<span data-ttu-id="1d719-104">Wenn ein Mitarbeiter Ihre Organisation verlässt, müssen Sie den Zugriff auf Microsoft 365 blockieren.</span><span class="sxs-lookup"><span data-stu-id="1d719-104">When an employee leaves your organization, on good terms or bad, you need to block their access to Microsoft 365.</span></span> <span data-ttu-id="1d719-105">Hier einige Möglichkeiten, wie Sie vorgehen können.</span><span class="sxs-lookup"><span data-stu-id="1d719-105">Here are a few ways you can do that.</span></span>
  
|<span data-ttu-id="1d719-106">Möglichkeiten zum Blockieren des Zugriffs</span><span class="sxs-lookup"><span data-stu-id="1d719-106">Way to block access</span></span>|<span data-ttu-id="1d719-107">Definition</span><span class="sxs-lookup"><span data-stu-id="1d719-107">Definition</span></span>|<span data-ttu-id="1d719-108">Bewährte Methode</span><span class="sxs-lookup"><span data-stu-id="1d719-108">Best practice</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1d719-109">Anmeldung blockieren</span><span class="sxs-lookup"><span data-stu-id="1d719-109">Block sign-in</span></span>  <br/> |<span data-ttu-id="1d719-110">Eine Möglichkeit, einen Benutzer am Zugriff auf Microsoft 365 zu hindern, besteht darin, den Anmeldestatus in **"Anmeldung blockiert"** zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1d719-110">One way to block a user from accessing Microsoft 365 is to change their sign-in status to **Sign-in blocked**.</span></span> <span data-ttu-id="1d719-111">Dadurch wird verhindert, dass sie sich von ihren Computern und mobilen Geräten bei Microsoft 365 anmelden, obwohl sie zuvor heruntergeladene oder synchronisierte E-Mails und Dokumente weiterhin anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="1d719-111">This prevents them from signing into Microsoft 365 from their computers and mobile devices though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="1d719-112">Wenn Sie Blackberry Enterprise Service verwenden, können Sie auch deren Zugriff dort deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1d719-112">If you're using Blackberry Enterprise Service, you can disable their access there as well.</span></span>  <br/> |<span data-ttu-id="1d719-113">Verwenden Sie diese Option, wenn ein Mitarbeiter plant, die Organisation zu verlassen oder langfristig abwesend sein wird.</span><span class="sxs-lookup"><span data-stu-id="1d719-113">Use when an employee plans to leave the organization or they plan to take a long-term leave of absence.</span></span>  <br/> |
|<span data-ttu-id="1d719-114">Benutzerkennwort zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="1d719-114">Reset user password</span></span>  <br/> |<span data-ttu-id="1d719-115">Eine weitere Möglichkeit, um zu verhindern, dass ein Benutzer auf Microsoft 365 zugreift, besteht darin, sein Kennwort zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="1d719-115">Another way to prevent a user from accessing Microsoft 365 is to reset their password.</span></span> <span data-ttu-id="1d719-116">Damit wird verhindert, dass das Konto genutzt wird, der Benutzer kann jedoch weiterhin heruntergeladene oder synchronisierte E-Mails und Dokumente anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1d719-116">This prevents them from using their account though they can still view previously downloaded or synced email and documents.</span></span> <span data-ttu-id="1d719-117">Sie können sich unter dem Namen des Benutzers anmelden und das Kennwort in ein von Ihnen gewähltes ändern.</span><span class="sxs-lookup"><span data-stu-id="1d719-117">You can then sign in as them and change the password to one of your choosing.</span></span>  <br/> |<span data-ttu-id="1d719-118">Verwenden Sie diese Option, wenn ein Mitarbeiter die Organisation unvermittelt und dauerhaft verlässt und Sie sich Sorgen um die Geschäftsdaten machen.</span><span class="sxs-lookup"><span data-stu-id="1d719-118">Use when an employee leaves suddenly and permanently and you feel there is concern for business data.</span></span>  <br/> |
|<span data-ttu-id="1d719-119">Alle zugewiesenen Lizenzen entfernen</span><span class="sxs-lookup"><span data-stu-id="1d719-119">Remove all assigned licenses</span></span>  <br/> |<span data-ttu-id="1d719-120">Eine weitere Möglichkeit besteht darin, alle Microsoft 365 Lizenzen zu entfernen, die dem Benutzer zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="1d719-120">Another option is to remove any Microsoft 365 licenses assigned to the user.</span></span> <span data-ttu-id="1d719-121">Damit wird verhindert, dass der Benutzer Anwendungen und Dienste wie die Office-Suite, Office-Apps für das Web, Yammer und SharePoint Online verwendet.</span><span class="sxs-lookup"><span data-stu-id="1d719-121">This prevents them from using applications and services like the Office suite, Office apps for the web, Yammer, and SharePoint Online.</span></span> <span data-ttu-id="1d719-122">Der Benutzer kann sich zwar weiterhin anmelden, kann jedoch nicht mehr auf diese Dienste zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1d719-122">They can still sign in but cannot use these services.</span></span>  <br/> |<span data-ttu-id="1d719-123">Verwenden Sie dies, wenn Sie der Meinung sind, dass dieser Benutzer keinen Zugriff mehr auf bestimmte Features in Microsoft 365 benötigt.</span><span class="sxs-lookup"><span data-stu-id="1d719-123">Use when you feel this user no longer needs access to specific features in Microsoft 365.</span></span>  <br/> <br> <span data-ttu-id="1d719-124">**Wichtig:** Wenn Sie eine Lizenz entfernen, wird das Postfach des Benutzers nach 30 Tagen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1d719-124">**Important:** When you remove a license, the user's mailbox will be deleted in 30 days.</span></span>
   
## <a name="related-articles"></a><span data-ttu-id="1d719-125">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="1d719-125">Related articles</span></span>

[<span data-ttu-id="1d719-126">Offboarding eines Benutzers aus Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1d719-126">Offboard a user from Microsoft 365</span></span>](../add-users/remove-former-employee.md)
    
[<span data-ttu-id="1d719-127">Zurücksetzen des Kennworts eines Benutzers in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1d719-127">Reset a user's password in Microsoft 365</span></span>](../add-users/reset-passwords.md)
    
[<span data-ttu-id="1d719-128">Zuweisen von Lizenzen zu Benutzern in Microsoft 365 for Business</span><span class="sxs-lookup"><span data-stu-id="1d719-128">Assign licenses to users in Microsoft 365 for business</span></span>](../manage/assign-licenses-to-users.md)
    
[<span data-ttu-id="1d719-129">Entfernen von Lizenzen von Benutzern in Microsoft 365 for Business</span><span class="sxs-lookup"><span data-stu-id="1d719-129">Remove licenses from users in Microsoft 365 for business</span></span>](../manage/remove-licenses-from-users.md)
    

