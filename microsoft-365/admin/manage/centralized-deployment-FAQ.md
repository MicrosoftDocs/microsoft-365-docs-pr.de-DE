---
title: FAQ zur zentralen Bereitstellung
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Lesen Sie die Antworten auf häufige Fragen zur zentralen Bereitstellung im Microsoft 365 Admin Center.
ms.openlocfilehash: 60d7a91da738803976b6823009450124d7b57814
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579302"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="efd2f-103">FAQ zur zentralen Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="efd2f-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="efd2f-104">Die zentrale Bereitstellung ist die empfohlene Möglichkeit für einen Office 365-Administrator zum Bereitstellen von Office-Add-Ins (Word, Excel, PowerPoint und Outlook) für Benutzer und Gruppen innerhalb einer Organisation, sofern die Organisation alle Anforderungen für die Verwendung der zentralisierten Bereitstellung wie in diesem Artikel beschrieben erfüllt.</span><span class="sxs-lookup"><span data-stu-id="efd2f-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="efd2f-105">Wo kann ich wissen, ob meine Organisation für die zentrale Bereitstellung eingerichtet ist?</span><span class="sxs-lookup"><span data-stu-id="efd2f-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="efd2f-106">Die zentrale Bereitstellung von Add-Ins erfordert, dass Benutzer Microsoft 365 Apps for Enterprise verwenden (und mit ihren Anmeldeinformationen für die Organisation bei Office angemeldet sind) und über Exchange Online verfügen.</span><span class="sxs-lookup"><span data-stu-id="efd2f-106">Centralized deployment of add-ins requires that users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="efd2f-107">Ihr Abonnementverzeichnis muss sich entweder in einem Partnerverzeichnis oder einem Partnerverzeichnis Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="efd2f-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="efd2f-108">Die zentrale Bereitstellung wird nur für Onlinepostfächer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="efd2f-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="efd2f-109">Die Bereitstellung in lokalen Postfächern wird Exchange unterstützt.</span><span class="sxs-lookup"><span data-stu-id="efd2f-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>

<span data-ttu-id="efd2f-110">Sie können die [Kompatibilitätsprüfung für](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)die zentrale Bereitstellung verwenden, um   festzustellen, ob Ihr Abonnement berechtigt ist.</span><span class="sxs-lookup"><span data-stu-id="efd2f-110">You can use the [Centralized Deployment Compatibility Checker](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="efd2f-111">Wie zielen Sie auf Add-In-Benutzerzuweisungen mit zentraler Bereitstellung ab?</span><span class="sxs-lookup"><span data-stu-id="efd2f-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="efd2f-112">Die zentrale Bereitstellung unterstützt Zuordnungen für einzelne Benutzer, Gruppen und alle Personen im Mandanten.</span><span class="sxs-lookup"><span data-stu-id="efd2f-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="efd2f-113">Die zentrale Bereitstellung kann für Benutzer in Gruppen der obersten Ebene oder Gruppen ohne übergeordnete Gruppen verwendet werden, jedoch nicht für Benutzer in geschachtelten Gruppen oder Gruppen mit übergeordneten Gruppen.</span><span class="sxs-lookup"><span data-stu-id="efd2f-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="efd2f-114">Die zentrale Bereitstellung ist auch Teil der meisten Azure Active Directory, einschließlich Office 365, Verteilerlisten und Sicherheitsgruppen.</span><span class="sxs-lookup"><span data-stu-id="efd2f-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="efd2f-115">Es ist besser, Gruppenzuweisungen anstelle einzelner Benutzerzuweisungen zu verwenden, um die Verwaltung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="efd2f-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="efd2f-116">Weitere Informationen finden Sie unter [Benutzer- und Gruppenzuweisungen](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments).</span><span class="sxs-lookup"><span data-stu-id="efd2f-116">For more details, see [User and Group assignments](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="efd2f-117">Wie lange dauert es, bis Add-Ins für alle Benutzer verfügbar sind?</span><span class="sxs-lookup"><span data-stu-id="efd2f-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="efd2f-118">Es kann bis zu 24 Stunden dauern, bis ein Add-In für alle Benutzer verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="efd2f-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="efd2f-119">Es kann dieselbe Zeit für Add-In-Updates, Änderungen beim Aktivieren oder Deaktivieren oder Entfernen von Add-Ins dauern.</span><span class="sxs-lookup"><span data-stu-id="efd2f-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="efd2f-120">Wie verwalte ich als Administrator den Benutzerzugriff auf Add-Ins für meine Organisation?</span><span class="sxs-lookup"><span data-stu-id="efd2f-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="efd2f-121">Zur einfachen Bereitstellung von Add-Ins für Benutzer, Gruppen oder ihre gesamte Organisation wird empfohlen, dass Administratoren die zentrale Bereitstellung verwenden.</span><span class="sxs-lookup"><span data-stu-id="efd2f-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="efd2f-122">Weitere Informationen zum Verwalten des Benutzerzugriffs finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="efd2f-122">For more information about managing user access, see:</span></span>
 - [<span data-ttu-id="efd2f-123">Verhindern von Add-In-Downloads durch Deaktivieren der Office Store für alle Clients (außer Outlook)</span><span class="sxs-lookup"><span data-stu-id="efd2f-123">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [<span data-ttu-id="efd2f-124">Festlegen der Administratoren und Benutzer, die Add-Ins für Outlook installieren und verwalten dürfen</span><span class="sxs-lookup"><span data-stu-id="efd2f-124">Specify the administrators and users who can install and manage add-ins for Outlook</span></span>](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="efd2f-125">Bietet die zentrale Bereitstellung Administratoren die Flexibilität, die Bereitstellungsmethode für Outlook zu wählen?</span><span class="sxs-lookup"><span data-stu-id="efd2f-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="efd2f-126">Ja.</span><span class="sxs-lookup"><span data-stu-id="efd2f-126">Yes.</span></span> <span data-ttu-id="efd2f-127">Die zentrale Bereitstellung bietet Administratoren die Flexibilität, während der Add-In-Bereitstellung eine von drei Bereitstellungsmethoden für Outlook-Add-Ins zu wählen:</span><span class="sxs-lookup"><span data-stu-id="efd2f-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="efd2f-128">**Fixed (Standard)**   Das Add-In wird automatisch für die zugewiesenen Benutzer bereitgestellt und kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="efd2f-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="efd2f-129">**Verfügbar** Benutzer können das Add-In in Outlook installieren, indem > **"Weitere Add-Ins > verwalten" auswählen.**</span><span class="sxs-lookup"><span data-stu-id="efd2f-129">**Available** Users can install the add-in in Outlook by choosing **Home > Get More add-ins > Admin-managed**.</span></span>
 
<span data-ttu-id="efd2f-130">**Optional** Das Add-In wird automatisch für die zugewiesenen Benutzer bereitgestellt, kann es jedoch entfernen.</span><span class="sxs-lookup"><span data-stu-id="efd2f-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="efd2f-131">Können Administratoren Branchen-Add-Ins aktualisieren?</span><span class="sxs-lookup"><span data-stu-id="efd2f-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="efd2f-132">Ja.</span><span class="sxs-lookup"><span data-stu-id="efd2f-132">Yes.</span></span> <span data-ttu-id="efd2f-133">Administratoren können eine neue Manifestdatei hochladen, um Metadatenänderungen für vom Administrator bereitgestellte BRANCHEN-Add-Ins zu unterstützen. Das Add-In wird beim nächsten Start der Office aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="efd2f-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="efd2f-134">Die Webanwendung kann sich jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="efd2f-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="efd2f-135">Weitere Informationen finden Sie unter [Line-of-Business-Add-In](./manage-addins-in-the-admin-center.md).</span><span class="sxs-lookup"><span data-stu-id="efd2f-135">For more information, see [line-of-business add-in](./manage-addins-in-the-admin-center.md).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="efd2f-136">Können Administratoren Add-Ins deaktivieren?</span><span class="sxs-lookup"><span data-stu-id="efd2f-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="efd2f-137">Ja.</span><span class="sxs-lookup"><span data-stu-id="efd2f-137">Yes.</span></span> <span data-ttu-id="efd2f-138">Administratoren können die von ihnen für alle Benutzer bereitgestellten Add-Ins aus dem Microsoft Admin Center aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="efd2f-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="efd2f-139">Weitere Informationen finden Sie unter [Add-In-Zustände](./manage-addins-in-the-admin-center.md#add-in-states).</span><span class="sxs-lookup"><span data-stu-id="efd2f-139">For more information, see [Add-in states](./manage-addins-in-the-admin-center.md#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="efd2f-140">Können Administratoren Add-Ins löschen oder entfernen?</span><span class="sxs-lookup"><span data-stu-id="efd2f-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="efd2f-141">Ja.</span><span class="sxs-lookup"><span data-stu-id="efd2f-141">Yes.</span></span> <span data-ttu-id="efd2f-142">Administratoren können für alle Benutzer bereitgestellte Add-Ins aus dem Microsoft Admin Center löschen.</span><span class="sxs-lookup"><span data-stu-id="efd2f-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="efd2f-143">Weitere Informationen finden Sie unter [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span><span class="sxs-lookup"><span data-stu-id="efd2f-143">For more information, see [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="efd2f-144">Können Administratoren kostenpflichtige Add-Ins aus dem Office Store zentrale Bereitstellung bereitstellen?</span><span class="sxs-lookup"><span data-stu-id="efd2f-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="efd2f-145">Nein.</span><span class="sxs-lookup"><span data-stu-id="efd2f-145">No.</span></span> <span data-ttu-id="efd2f-146">Sie können zurzeit keine kostenpflichtigen Add-Ins aus dem Office Store zentrale Bereitstellung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="efd2f-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="efd2f-147">Wir empfehlen, den ISV-Entwickler für das kostenpflichtige Add-In zu erreichen, um eine Manifestdatei oder eine URL an fordern.</span><span class="sxs-lookup"><span data-stu-id="efd2f-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="efd2f-148">Der Mandantenadministrator kann das Add-In dann mithilfe der zentralisierten Bereitstellung als Branchen-Add-In bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="efd2f-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="efd2f-149">Welche Administratorrolle muss ich zum Verwalten von Add-Ins für meine Organisation verwenden?</span><span class="sxs-lookup"><span data-stu-id="efd2f-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="efd2f-150">Globaler Administrator ist die empfohlene Rolle mit vollständigem Zugriff auf den Add-In-Verwaltungslebenszyklus.</span><span class="sxs-lookup"><span data-stu-id="efd2f-150">Global Admin is the recommended role with complete access to add-in management lifecycle.</span></span> <span data-ttu-id="efd2f-151">Andere Administratorrollen haben einen eingeschränkten Zugriff auf den Add-In-Bereitstellungslebenszyklus.</span><span class="sxs-lookup"><span data-stu-id="efd2f-151">Other Admin roles have a limited access to add-in deployment lifecycle.</span></span> <span data-ttu-id="efd2f-152">Wenn Sie die Person sind, die Ihr Microsoft 365 business-Abonnement erworben hat, sind Sie der globale Administrator.</span><span class="sxs-lookup"><span data-stu-id="efd2f-152">If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="efd2f-153">Ihr Abonnement enthält eine Reihe von Administratorrollen, die Sie anderen Benutzern in Ihrer Organisation zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="efd2f-153">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="efd2f-154">Jede Administratorrolle ordnet allgemeine Geschäftsfunktionen zu und erteilt Personen in Ihrer Organisation die Berechtigung, bestimmte Aufgaben im Microsoft 365 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="efd2f-154">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="efd2f-155">Weitere Informationen finden Sie unter [Zuweisen von Administratorrollen](../add-users/assign-admin-roles.md?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="efd2f-155">For more information, see [Assign admin roles](../add-users/assign-admin-roles.md?view=o365-worldwide).</span></span> 