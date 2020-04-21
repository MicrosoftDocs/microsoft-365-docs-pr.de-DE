---
title: Wählen Sie die Domäne aus, die beim Erstellen von Microsoft 365-Gruppen verwendet werden soll.
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: 'Hier erfahren Sie, wie Sie die zu verwendende Domäne beim Erstellen von Microsoft 365-Gruppen auswählen, indem Sie e-Mail-Adress Richtlinien mithilfe von PowerShell konfigurieren '
ms.openlocfilehash: 1bc8a160ffc368bc4c66a5ac17ffcb203dc678f5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630623"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="9091c-103">Wählen Sie die Domäne aus, die beim Erstellen von Microsoft 365-Gruppen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9091c-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

 <span data-ttu-id="9091c-104">Einige Organisationen verwenden separate E-Mail-Domänen, um unterschiedliche Unternehmensbereiche zu segmentieren.</span><span class="sxs-lookup"><span data-stu-id="9091c-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="9091c-105">Sie können angeben, welche Domäne verwendet werden soll, wenn Ihre Benutzer Microsoft 365-Gruppen erstellen.</span><span class="sxs-lookup"><span data-stu-id="9091c-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="9091c-106">Wenn Benutzer in Ihrer Organisation ihre Gruppen in anderen Domänen als der akzeptierten Standarddomäne Ihres Unternehmens erstellen müssen, können Sie dies erlauben, indem Sie E-Mail-Adressrichtlinien (Email Address Policies, EAPs) mithilfe von PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9091c-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>
  
<span data-ttu-id="9091c-107">Bevor Sie die PowerShell-Cmdlets ausführen können, müssen Sie ein Modul herunterladen und installieren, mit dem Sie mit Ihrer Organisation in Gespräch treten können.</span><span class="sxs-lookup"><span data-stu-id="9091c-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="9091c-108">Lesen Sie [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span><span class="sxs-lookup"><span data-stu-id="9091c-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>
  
## <a name="example-scenarios"></a><span data-ttu-id="9091c-109">Beispielszenarien</span><span class="sxs-lookup"><span data-stu-id="9091c-109">Example scenarios</span></span>

<span data-ttu-id="9091c-110">Angenommen, die Hauptdomäne Ihres Unternehmens lautet contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9091c-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="9091c-111">Die akzeptierte Standarddomäne Ihrer Organisation ist jedoch Service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="9091c-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="9091c-112">Dies bedeutet, dass Gruppen in Service.contoso.com erstellt werden (beispielsweise jimsteam@Service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="9091c-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="9091c-113">Weiterhin angenommen, Sie haben in Ihrer Organisation auch Unterdomänen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9091c-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="9091c-114">Sie möchten auch, dass Gruppen in diesen Domänen erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="9091c-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="9091c-115">students.contoso.com für Studierende</span><span class="sxs-lookup"><span data-stu-id="9091c-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="9091c-116">faculty.contoso.com für Lehrkräfte</span><span class="sxs-lookup"><span data-stu-id="9091c-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="9091c-117">Anhand der beiden folgenden Szenarien wird erläutert, wie Sie dies erreichen können.</span><span class="sxs-lookup"><span data-stu-id="9091c-117">The following two scenarios explain how you would accomplish this.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9091c-118">Wenn Sie mehreren Stand eaps haben, werden Sie in der Reihenfolge der Priorität ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="9091c-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="9091c-119">Der Wert 1 bedeutet die höchste Priorität.</span><span class="sxs-lookup"><span data-stu-id="9091c-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="9091c-120">Wenn ein EAP übereinstimmt, wird kein weiterer EAP ausgewertet, und Adressen, die auf die Gruppe gestempelt werden, entsprechen dem entsprechenden EAP.</span><span class="sxs-lookup"><span data-stu-id="9091c-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="9091c-121">> Wenn kein eaps mit den angegebenen Kriterien übereinstimmt, wird die Gruppe in der standardmäßigen akzeptierten Domäne der Organisation festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9091c-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="9091c-122">Weitere Informationen zum Hinzufügen einer akzeptierten Domäne finden Sie [unter Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) .</span><span class="sxs-lookup"><span data-stu-id="9091c-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span> 
  
### <a name="scenario-1"></a><span data-ttu-id="9091c-123">Szenario 1</span><span class="sxs-lookup"><span data-stu-id="9091c-123">Scenario 1</span></span>

<span data-ttu-id="9091c-124">Das folgende Beispiel zeigt, wie Sie alle Microsoft 365-Gruppen in Ihrer Organisation in der Groups.contoso.com-Domäne anbieten.</span><span class="sxs-lookup"><span data-stu-id="9091c-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="9091c-125">Szenario 2</span><span class="sxs-lookup"><span data-stu-id="9091c-125">Scenario 2</span></span>

<span data-ttu-id="9091c-126">Angenommen, Sie möchten steuern, in welchen Unterdomänen Microsoft 365-Gruppen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9091c-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="9091c-127">Du willst:</span><span class="sxs-lookup"><span data-stu-id="9091c-127">You want:</span></span>
  
- <span data-ttu-id="9091c-128">Gruppen, die von Teilnehmern (Benutzer mit **Abteilungs** Einstellungen für **Schüler**) in der students.Groups.contoso.com-Domäne erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="9091c-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="9091c-129">Verwenden Sie dazu diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="9091c-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="9091c-130">Von Fakultätsmitgliedern erstellte Gruppen (Benutzer, die eine **Abteilung** für die **Fakultät oder die e-Mail-Adresse enthalten Faculty.contoso.com)**) in der Faculty.Groups.contoso.com-Domäne.</span><span class="sxs-lookup"><span data-stu-id="9091c-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="9091c-131">Verwenden Sie dazu diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="9091c-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="9091c-132">Alle anderen Benutzer sollen in der Domäne "groups.contoso.com" erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="9091c-132">All other users in the groups.contoso.com domain.</span></span> <span data-ttu-id="9091c-133">Verwenden Sie dazu diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="9091c-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="9091c-134">Ändern von E-Mail-Adressrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9091c-134">Change email address policies</span></span>

<span data-ttu-id="9091c-135">Zum Ändern der Priorität oder von E-Mail-Adressvorlagen für eine vorhandene EAP verwenden Sie das Cmdlet "Set-EmailAddressPolicy".</span><span class="sxs-lookup"><span data-stu-id="9091c-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="9091c-136">Die Änderung einer EAP hat keine Auswirkungen auf die bereits bereitgestellten Gruppen.</span><span class="sxs-lookup"><span data-stu-id="9091c-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="9091c-137">Löschen von E-Mail-Adressrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9091c-137">Delete email address policies</span></span>

<span data-ttu-id="9091c-138">Zum Löschen einer EAP verwenden Sie das Cmdlet "Remove-EmailAddressPolicy".</span><span class="sxs-lookup"><span data-stu-id="9091c-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="9091c-139">Die Änderung einer EAP hat keine Auswirkungen auf die bereits bereitgestellten Gruppen.</span><span class="sxs-lookup"><span data-stu-id="9091c-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="9091c-140">Anforderungen für Hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="9091c-140">Hybrid requirements</span></span>

<span data-ttu-id="9091c-141">Wenn Ihre Organisation in einem Hybrid Szenario konfiguriert ist, lesen Sie [configure Microsoft 365 groups with on-premises Exchange Hybrid](https://go.microsoft.com/fwlink/p/?LinkId=785430) , um sicherzustellen, dass Ihre Organisation die Anforderungen zum Erstellen von Microsoft 365-Gruppen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="9091c-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/p/?LinkId=785430) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="9091c-142">Weitere Informationen zur Verwendung von Gruppen mit e-Mail-Adress Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="9091c-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="9091c-143">Es gibt ein paar weitere Punkte, die Sie wissen müssen:</span><span class="sxs-lookup"><span data-stu-id="9091c-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="9091c-144">Wie schnell Gruppen erstellt werden, ist von der Anzahl der in Ihrer Organisation konfigurierten EAPs abhängig.</span><span class="sxs-lookup"><span data-stu-id="9091c-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="9091c-145">Administratoren und Benutzer können Domänen beim Erstellen von Gruppen auch ändern.</span><span class="sxs-lookup"><span data-stu-id="9091c-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="9091c-146">Die Gruppe der Benutzer wird mithilfe der bereits verfügbaren Standardabfragen (Benutzereigenschaften) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="9091c-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="9091c-147">Überprüfen Sie [die filterbaren Eigenschaften für den Parameter "-RecipientFilter"](https://go.microsoft.com/fwlink/p/?LinkId=785918) für unterstützte Filterbare Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="9091c-147">Check out [Filterable properties for the -RecipientFilter parameter](https://go.microsoft.com/fwlink/p/?LinkId=785918) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="9091c-148">Wenn Sie keine EAPs für Gruppen konfigurieren, wird die akzeptierte Standarddomäne für die Gruppenerstellung ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="9091c-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="9091c-149">Wenn Sie eine akzeptierte Domäne entfernen möchten, müssen Sie zuerst die EAPs aktualisieren, andernfalls hat dies Auswirkungen auf die Gruppenbereitstellung.</span><span class="sxs-lookup"><span data-stu-id="9091c-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="9091c-150">Für eine Organisation können maximal 100 E-Mail-Adressrichtlinien konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="9091c-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="9091c-151">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="9091c-151">Related articles</span></span>

[<span data-ttu-id="9091c-152">Erstellen einer Microsoft 365-Gruppe im Admin Center</span><span class="sxs-lookup"><span data-stu-id="9091c-152">Create an Microsoft 365 group in the admin center</span></span>](create-groups.md)
