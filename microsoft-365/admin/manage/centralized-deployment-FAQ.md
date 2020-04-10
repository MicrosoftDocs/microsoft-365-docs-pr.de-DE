---
title: FAQ zur zentralen Bereitstellung
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
description: Lesen Sie die Antworten auf häufige Fragen zur zentralisierten Bereitstellung im Microsoft 365 Admin Center.
ms.openlocfilehash: 39df2ec5a1671f800572bc845581bdbe2716d209
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43209664"
---
# <a name="centralized-deployment-faq"></a><span data-ttu-id="a2197-103">FAQ zur zentralen Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="a2197-103">Centralized Deployment FAQ</span></span>

<span data-ttu-id="a2197-104">Die zentralisierte Bereitstellung ist die empfohlene Vorgehensweise für einen Office 365 Administrator zum Bereitstellen von Office-Add-Ins (Word, Excel, PowerPoint und Outlook) für Benutzer und Gruppen in einer Organisation, vorausgesetzt, die Organisation erfüllt alle Anforderungen für die Verwendung einer zentralisierten Bereitstellung, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a2197-104">Centralized Deployment is the recommended way for an Office 365 admin to deploy Office add-ins (Word, Excel, PowerPoint, and Outlook) to users and groups within an organization, provided the organization meets all requirements for using Centralized Deployment as outlined in this article.</span></span>   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a><span data-ttu-id="a2197-105">Woher weiß ich, ob meine Organisation für die zentrale Bereitstellung eingerichtet ist?</span><span class="sxs-lookup"><span data-stu-id="a2197-105">How do I know if my organization is set up for Centralized Deployment?</span></span>  

<span data-ttu-id="a2197-106">Die zentrale Bereitstellung von Add-ins erfordert, dass Benutzer Office 365 ProPlus verwenden (und mit Ihren Anmeldeinformationen für die organisatorische Anmeldung bei Office angemeldet sind) und über Exchange Online Postfächer verfügen.</span><span class="sxs-lookup"><span data-stu-id="a2197-106">Centralized deployment of add-ins requires that users are using Office 365 ProPlus (and are signed into Office using their organizational log-in credentials) and have Exchange Online mailboxes.</span></span> <span data-ttu-id="a2197-107">Ihr Abonnement Verzeichnis muss sich entweder in oder im Verbund mit, Azure Active Directory befinden.</span><span class="sxs-lookup"><span data-stu-id="a2197-107">Your subscription directory must either be in, or federated to, Azure Active Directory.</span></span>  
 
<span data-ttu-id="a2197-108">Die zentralisierte Bereitstellung wird nur für Online Postfächer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a2197-108">Centralized Deployment is only supported for online mailboxes.</span></span> <span data-ttu-id="a2197-109">Die Bereitstellung für lokale Exchange-Postfächer wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a2197-109">It does not support deployment to on-premises Exchange mailboxes.</span></span>
 
<span data-ttu-id="a2197-110">Sie können die [Office 365 zentrale Bereitstellungs Kompatibilitätsprüfung](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker) verwenden, um zu ermitteln, ob Ihr Abonnement berechtigt ist.</span><span class="sxs-lookup"><span data-stu-id="a2197-110">You can use the [Office 365 Centralized Deployment Compatibility Checker](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker) to determine if your subscription is eligible.</span></span> 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a><span data-ttu-id="a2197-111">Wie Zielen Sie auf Add-in-Benutzerzuweisungen mit zentralisierter Bereitstellung ab?</span><span class="sxs-lookup"><span data-stu-id="a2197-111">How do you target add-in user assignments with Centralized Deployment?</span></span>  

<span data-ttu-id="a2197-112">Die zentralisierte Bereitstellung unterstützt Zuweisungen für einzelne Benutzer, Gruppen und alle Personen im Mandanten.</span><span class="sxs-lookup"><span data-stu-id="a2197-112">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="a2197-113">Die zentralisierte Bereitstellung kann für Benutzer in Gruppen oder Gruppen auf oberster Ebene ohne übergeordnete Gruppen verwendet werden, jedoch nicht für Benutzer in geschachtelten Gruppen oder Gruppen, die übergeordnete Gruppen haben.</span><span class="sxs-lookup"><span data-stu-id="a2197-113">Centralized Deployment can be used for users in top-level groups or groups without parent groups, but not for users in nested groups or groups that have parent groups.</span></span> <span data-ttu-id="a2197-114">Die zentralisierte Bereitstellung ist auch Teil der meisten Azure Active Directory-Gruppen, einschließlich Office 365 Gruppen, Verteilerlisten und Sicherheitsgruppen.</span><span class="sxs-lookup"><span data-stu-id="a2197-114">Centralized Deployment is also part of most Azure Active Directory groups, including Office 365 Groups, distribution lists, and security groups.</span></span>  

<span data-ttu-id="a2197-115">Es ist besser, Gruppenzuweisungen anstelle der einzelnen Benutzerzuweisungen zu verwenden, um die Verwaltung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="a2197-115">It is better to use groups assignments instead of individual user assignment for easier management.</span></span>
 
<span data-ttu-id="a2197-116">Weitere Informationen finden Sie unter [Benutzer-und Gruppenzuweisungen](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span><span class="sxs-lookup"><span data-stu-id="a2197-116">For more details, see [User and Group assignments](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).</span></span>  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a><span data-ttu-id="a2197-117">Wie lange dauert es, bis Add-Ins für alle Benutzer angezeigt werden?</span><span class="sxs-lookup"><span data-stu-id="a2197-117">How long does it take for add-ins to show up for all users?</span></span>  

<span data-ttu-id="a2197-118">Es kann bis zu 24 Stunden dauern, bis ein Add-in für alle Benutzer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a2197-118">It can take up to 24 hours for an add-in to show up for all users.</span></span> <span data-ttu-id="a2197-119">Es kann die gleiche Zeit für Add-in-Updates, Änderungen von ein-oder ausschalten oder Add-in-Entfernungen dauern.</span><span class="sxs-lookup"><span data-stu-id="a2197-119">It can take the same amount of time for add-in updates, changes from turn on or turn off, or add-in removals.</span></span> 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a><span data-ttu-id="a2197-120">Wie kann ich als Administrator den Benutzer Zugriff auf Add-Ins für meine Organisation verwalten?</span><span class="sxs-lookup"><span data-stu-id="a2197-120">As an administrator, how do I manage the user access to add-ins for my organization?</span></span>

<span data-ttu-id="a2197-121">Für eine einfache Bereitstellung von Add-Ins für Benutzer, Gruppen oder für Ihre gesamte Organisation wird empfohlen, dass Administratoren eine zentralisierte Bereitstellung verwenden.</span><span class="sxs-lookup"><span data-stu-id="a2197-121">For easy deployment of add-ins to users, groups, or to your entire organization, we recommend administrators use Centralized Deployment.</span></span>

<span data-ttu-id="a2197-122">Weitere Informationen zum Verwalten des Benutzerzugriffs finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="a2197-122">For more information about managing user access, see</span></span> </br><span data-ttu-id="a2197-123">[Verhindern von Add-in-Downloads durch Deaktivieren der Office Store für alle Clients (außer Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) und</span><span class="sxs-lookup"><span data-stu-id="a2197-123">[Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) and</span></span> </br><span data-ttu-id="a2197-124">[Geben Sie die Administratoren und Benutzer an, die Add-Ins für Outlook installieren und verwalten können](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN).</span><span class="sxs-lookup"><span data-stu-id="a2197-124">[Specify the administrators and users who can install and manage add-ins for Outlook](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN).</span></span>

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a><span data-ttu-id="a2197-125">Bietet die zentralisierte Bereitstellung Administratoren die Flexibilität, die Bereitstellungsmethode für Outlook-Add-Ins auszuwählen?</span><span class="sxs-lookup"><span data-stu-id="a2197-125">Will Centralized Deployment provide admins the flexibility to choose the deployment method for Outlook add-ins?</span></span>  

<span data-ttu-id="a2197-126">Ja.</span><span class="sxs-lookup"><span data-stu-id="a2197-126">Yes.</span></span> <span data-ttu-id="a2197-127">Die zentralisierte Bereitstellung bietet Administratoren die Möglichkeit, während der Add-in-Bereitstellung eine von drei Bereitstellungsmethoden für Outlook-Add-Ins auszuwählen:</span><span class="sxs-lookup"><span data-stu-id="a2197-127">Centralized Deployment provides admins the flexibility to choose one of three deployment methods for Outlook add-ins during add-in deployment:</span></span>

<span data-ttu-id="a2197-128">**Fixed (Standard)**   das Add-in wird automatisch für die zugewiesenen Benutzer bereitgestellt und kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="a2197-128">**Fixed (Default)**  The add-in is deployed automatically to the assigned users, and they cannot remove it.</span></span>  
 
<span data-ttu-id="a2197-129">**Verfügbar** Benutzer können das Add-in in Outlook installieren, indem Sie "Home" auswählen > Weitere Add-Ins > admin-Managed hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a2197-129">**Available** Users can install the add-in in Outlook by choosing Home > Get More add-ins > Admin-managed.</span></span>   
 
<span data-ttu-id="a2197-130">**Optional** Das Add-in wird automatisch für die zugewiesenen Benutzer bereitgestellt, aber Sie können es auswählen, um es zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a2197-130">**Optional** The add-in is deployed automatically to the assigned users, but they can choose to remove it.</span></span>  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a><span data-ttu-id="a2197-131">Können Administratoren Lob-Add-Ins (Business) aktualisieren?</span><span class="sxs-lookup"><span data-stu-id="a2197-131">Can admins update Line-of-Business (LOB) add-ins?</span></span>  

<span data-ttu-id="a2197-132">Ja.</span><span class="sxs-lookup"><span data-stu-id="a2197-132">Yes.</span></span> <span data-ttu-id="a2197-133">Administratoren können eine neue Manifestdatei hochladen, um Änderungen an Metadaten für vom Administrator bereitgestellte Lob-Add-Ins zu unterstützen. Das Add-in wird aktualisiert, wenn die Office-Anwendungen das nächste Mal gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="a2197-133">Admins can upload a new manifest file to support metadata changes for admin-deployed LOB add-ins. The add-in updates the next time the Office applications starts.</span></span> <span data-ttu-id="a2197-134">Die Webanwendung kann sich jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="a2197-134">The web application can change at any time.</span></span>  
 
<span data-ttu-id="a2197-135">Weitere Informationen finden Sie unter Branchen [-Add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins).</span><span class="sxs-lookup"><span data-stu-id="a2197-135">For more information, see [line-of-business add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins).</span></span>  

## <a name="can-admins-turn-off-add-ins"></a><span data-ttu-id="a2197-136">Können Administratoren Add-Ins deaktivieren?</span><span class="sxs-lookup"><span data-stu-id="a2197-136">Can admins turn off add-ins?</span></span>  

<span data-ttu-id="a2197-137">Ja.</span><span class="sxs-lookup"><span data-stu-id="a2197-137">Yes.</span></span> <span data-ttu-id="a2197-138">Administratoren können die Add-Ins, die Sie für alle Benutzer aus dem Microsoft Admin Center bereitstellen, aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="a2197-138">Admins can turn on or off the add-ins they deploy for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="a2197-139">Weitere Informationen finden Sie unter [Add-in-Status](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states).</span><span class="sxs-lookup"><span data-stu-id="a2197-139">For more information, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states).</span></span>  

##  <a name="can-admins-delete-or-remove-add-ins"></a><span data-ttu-id="a2197-140">Können Administratoren Add-ins löschen oder entfernen?</span><span class="sxs-lookup"><span data-stu-id="a2197-140">Can admins delete or remove add-ins?</span></span>

<span data-ttu-id="a2197-141">Ja.</span><span class="sxs-lookup"><span data-stu-id="a2197-141">Yes.</span></span> <span data-ttu-id="a2197-142">Administratoren können Add-Ins, die Sie für alle Benutzer bereitgestellt haben, aus dem Microsoft Admin Center löschen.</span><span class="sxs-lookup"><span data-stu-id="a2197-142">Admins can delete add-ins they deployed for all users from the Microsoft admin center.</span></span>

<span data-ttu-id="a2197-143">Weitere Informationen finden Sie unter [delete the Add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in).</span><span class="sxs-lookup"><span data-stu-id="a2197-143">For more information, see [Delete the add-in](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in).</span></span> 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a><span data-ttu-id="a2197-144">Können Administratoren kostenpflichtige Add-Ins aus dem Office Store mithilfe einer zentralisierten Bereitstellung bereitstellen?</span><span class="sxs-lookup"><span data-stu-id="a2197-144">Can admins deploy paid add-ins from the Office Store using Centralized Deployment?</span></span> 

<span data-ttu-id="a2197-145">Nein.</span><span class="sxs-lookup"><span data-stu-id="a2197-145">No.</span></span> <span data-ttu-id="a2197-146">Sie können zu diesem Zeitpunkt keine kostenpflichtigen Add-Ins aus dem Office Store mithilfe einer zentralisierten Bereitstellung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a2197-146">You can't deploy paid add-ins from the Office Store using Centralized Deployment at this time.</span></span>  
 
<span data-ttu-id="a2197-147">Wir empfehlen, den ISV-Entwickler für das kostenpflichtige Add-in zu erreichen, um eine Manifestdatei oder eine URL anzufordern.</span><span class="sxs-lookup"><span data-stu-id="a2197-147">We suggest reaching out to the ISV Developer for the paid add-in to request a manifest file or a URL.</span></span> <span data-ttu-id="a2197-148">Der mandantenadministrator kann das Add-in dann mithilfe einer zentralisierten Bereitstellung als Lob-Add-in bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a2197-148">The tenant admin can then deploy the add-in as a LOB add-in using Centralized Deployment.</span></span>
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a><span data-ttu-id="a2197-149">Welche Administratorrolle muss ich für die Verwaltung von Add-Ins für meine Organisation übernehmen?</span><span class="sxs-lookup"><span data-stu-id="a2197-149">Which admin role do I need to manage add-ins for my organization?</span></span>  

<span data-ttu-id="a2197-150">Sie müssen über die globale Administratorrolle zum Verwalten von Add-Ins verfügen. Wenn Sie die Person sind, die Ihr Microsoft 365 for Business-Abonnement erworben hat, sind Sie der globale Administrator.</span><span class="sxs-lookup"><span data-stu-id="a2197-150">You must have the Global admin role to manage add-ins. If you're the person who purchased your Microsoft 365 for business subscription, you are the Global admin.</span></span> 
 
<span data-ttu-id="a2197-151">Ihr Abonnement verfügt über eine Reihe von Administratorrollen, die Sie anderen Benutzern in Ihrer Organisation zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="a2197-151">Your subscription comes with a set of admin roles that you can assign to other users in your organization.</span></span> <span data-ttu-id="a2197-152">Jede Administratorrolle ordnet allgemeine Geschäftsfunktionen zu und gibt Personen in Ihrer Organisation Berechtigungen zum Ausführen bestimmter Aufgaben im Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="a2197-152">Each admin role maps to common business functions and gives people in your organization permissions to perform specific tasks in the Microsoft 365 admin center.</span></span>  
 
<span data-ttu-id="a2197-153">Weitere Informationen finden Sie unter [Zuweisen von Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="a2197-153">For more information, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).</span></span>  