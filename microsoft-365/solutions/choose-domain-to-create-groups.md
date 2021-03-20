---
title: Auswählen der Domäne, die beim Erstellen von Microsoft 365-Gruppen verwendet werden soll
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: Erfahren Sie, wie Sie die Domäne auswählen, die beim Erstellen von Microsoft 365-Gruppen verwendet werden soll, indem Sie E-Mail-Adressrichtlinien mithilfe von PowerShell konfigurieren.
ms.openlocfilehash: 4908d5bd58ca6d0fbb50151983ddb459f0732284
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904684"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="f1447-103">Auswählen der Domäne, die beim Erstellen von Microsoft 365-Gruppen verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="f1447-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="f1447-104">Einige Organisationen verwenden separate E-Mail-Domänen, um unterschiedliche Unternehmensbereiche zu segmentieren.</span><span class="sxs-lookup"><span data-stu-id="f1447-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="f1447-105">Sie können angeben, welche Domäne beim Erstellen von Microsoft 365-Gruppen von Benutzern verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f1447-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="f1447-106">Wenn Benutzer in Ihrer Organisation ihre Gruppen in anderen Domänen als der akzeptierten Standarddomäne Ihres Unternehmens erstellen müssen, können Sie dies erlauben, indem Sie E-Mail-Adressrichtlinien (Email Address Policies, EAPs) mithilfe von PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f1447-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="f1447-107">Bevor Sie die PowerShell-Cmdlets ausführen können, laden Sie ein Modul herunter, mit dem Sie mit Ihrer Organisation sprechen können.</span><span class="sxs-lookup"><span data-stu-id="f1447-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="f1447-108">Lesen Sie [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f1447-108">Check out [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="f1447-109">Beispielszenarien</span><span class="sxs-lookup"><span data-stu-id="f1447-109">Example scenarios</span></span>

<span data-ttu-id="f1447-110">Angenommen, die Hauptdomäne Ihres Unternehmens ist Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f1447-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="f1447-111">Die standardmäßig akzeptierte Domäne Ihrer Organisation ist jedoch service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f1447-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="f1447-112">Dies bedeutet, dass Gruppen in service.contoso.com erstellt werden (z. B. jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f1447-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="f1447-113">Weiterhin angenommen, Sie haben in Ihrer Organisation auch Unterdomänen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="f1447-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="f1447-114">Sie möchten auch, dass Gruppen in diesen Domänen erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="f1447-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="f1447-115">students.contoso.com für Studierende</span><span class="sxs-lookup"><span data-stu-id="f1447-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="f1447-116">faculty.contoso.com für Lehrkräfte</span><span class="sxs-lookup"><span data-stu-id="f1447-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="f1447-117">Anhand der beiden folgenden Szenarien wird erläutert, wie Sie dies erreichen können.</span><span class="sxs-lookup"><span data-stu-id="f1447-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="f1447-118">Wenn Sie über Mulitple-EAPs verfügen, werden sie in der Reihenfolge ihrer Priorität ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="f1447-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="f1447-119">Der Wert 1 bedeutet die höchste Priorität.</span><span class="sxs-lookup"><span data-stu-id="f1447-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="f1447-120">Sobald ein EAP übereinstimmunget, wird keine weitere EAP ausgewertet, und Adressen, die für die Gruppe gestempelt werden, entsprechen dem übereinstimmenen EAP.</span><span class="sxs-lookup"><span data-stu-id="f1447-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="f1447-121">> Wenn keine EAPs den angegebenen Kriterien entsprechen, wird die Gruppe in der standardmäßig akzeptierten Domäne der Organisation bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f1447-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="f1447-122">Weitere Informationen zum Hinzufügen einer akzeptierten Domäne finden Sie unter Verwalten akzeptierter Domänen [in Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="f1447-122">Check out [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="f1447-123">Szenario 1</span><span class="sxs-lookup"><span data-stu-id="f1447-123">Scenario 1</span></span>

<span data-ttu-id="f1447-124">Das folgende Beispiel zeigt, wie Sie alle Microsoft 365-Gruppen in Ihrer Organisation in der groups.contoso.com bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f1447-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="f1447-125">Szenario 2</span><span class="sxs-lookup"><span data-stu-id="f1447-125">Scenario 2</span></span>

<span data-ttu-id="f1447-126">Angenommen, Sie möchten steuern, in welchen Unterdomänen Microsoft 365-Gruppen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f1447-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="f1447-127">Du willst:</span><span class="sxs-lookup"><span data-stu-id="f1447-127">You want:</span></span>
  
- <span data-ttu-id="f1447-128">Von Kursteilnehmern erstellte Gruppen (Benutzer, für die **Abteilung** auf Kursteilnehmer **festgelegt** ist) in students.groups.contoso.com Domäne.</span><span class="sxs-lookup"><span data-stu-id="f1447-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="f1447-129">Verwenden Sie dazu diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="f1447-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="f1447-130">Von Lehrkräften erstellte Gruppen (Benutzer, deren **Abteilung** auf Fakultät oder E-Mail-Adresse festgelegt ist, enthält **faculty.contoso.com)** in der faculty.groups.contoso.com Domäne.</span><span class="sxs-lookup"><span data-stu-id="f1447-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="f1447-131">Verwenden Sie dazu diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="f1447-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="f1447-132">Gruppen, die von anderen Personen erstellt werden, werden in der groups.contoso.com erstellt.</span><span class="sxs-lookup"><span data-stu-id="f1447-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="f1447-133">Verwenden Sie dazu diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="f1447-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="f1447-134">Ändern von E-Mail-Adressrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f1447-134">Change email address policies</span></span>

<span data-ttu-id="f1447-135">Zum Ändern der Priorität oder von E-Mail-Adressvorlagen für eine vorhandene EAP verwenden Sie das Cmdlet "Set-EmailAddressPolicy".</span><span class="sxs-lookup"><span data-stu-id="f1447-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="f1447-136">Die Änderung einer EAP hat keine Auswirkungen auf die bereits bereitgestellten Gruppen.</span><span class="sxs-lookup"><span data-stu-id="f1447-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="f1447-137">Löschen von E-Mail-Adressrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f1447-137">Delete email address policies</span></span>

<span data-ttu-id="f1447-138">Zum Löschen einer EAP verwenden Sie das Cmdlet "Remove-EmailAddressPolicy".</span><span class="sxs-lookup"><span data-stu-id="f1447-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="f1447-139">Die Änderung einer EAP hat keine Auswirkungen auf die bereits bereitgestellten Gruppen.</span><span class="sxs-lookup"><span data-stu-id="f1447-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="f1447-140">Anforderungen für Hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="f1447-140">Hybrid requirements</span></span>

<span data-ttu-id="f1447-141">Wenn Ihre Organisation in einem Hybridszenario konfiguriert ist, lesen Sie Konfigurieren von [Microsoft 365-Gruppen](/exchange/hybrid-deployment/set-up-microsoft-365-groups) mit einer lokalen Exchange-Hybridlösung, um sicherzustellen, dass Ihre Organisation die Anforderungen zum Erstellen von Microsoft 365-Gruppen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="f1447-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="f1447-142">Zusätzliche Informationen zur Verwendung von E-Mail-Adressrichtliniengruppen:</span><span class="sxs-lookup"><span data-stu-id="f1447-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="f1447-143">Es gibt ein paar weitere Punkte, die Sie wissen müssen:</span><span class="sxs-lookup"><span data-stu-id="f1447-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="f1447-144">Wie schnell Gruppen erstellt werden, ist von der Anzahl der in Ihrer Organisation konfigurierten EAPs abhängig.</span><span class="sxs-lookup"><span data-stu-id="f1447-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="f1447-145">Administratoren und Benutzer können domänen auch ändern, wenn sie Gruppen erstellen.</span><span class="sxs-lookup"><span data-stu-id="f1447-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="f1447-146">Die Gruppe der Benutzer wird mithilfe der bereits verfügbaren Standardabfragen (Benutzereigenschaften) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="f1447-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="f1447-147">Weitere Informationen [finden Sie unter Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span><span class="sxs-lookup"><span data-stu-id="f1447-147">Check out [Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="f1447-148">Wenn Sie keine EAPs für Gruppen konfigurieren, wird die akzeptierte Standarddomäne für die Gruppenerstellung ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="f1447-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="f1447-149">Wenn Sie eine akzeptierte Domäne entfernen möchten, müssen Sie zuerst die EAPs aktualisieren, andernfalls hat dies Auswirkungen auf die Gruppenbereitstellung.</span><span class="sxs-lookup"><span data-stu-id="f1447-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="f1447-150">Für eine Organisation können maximal 100 E-Mail-Adressrichtlinien konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f1447-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="f1447-151">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="f1447-151">Related articles</span></span>

[<span data-ttu-id="f1447-152">Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance</span><span class="sxs-lookup"><span data-stu-id="f1447-152">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="f1447-153">Erstellen eines Plans für die Zusammenarbeitsgovernance</span><span class="sxs-lookup"><span data-stu-id="f1447-153">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="f1447-154">Erstellen einer Microsoft 365-Gruppe im Admin Center</span><span class="sxs-lookup"><span data-stu-id="f1447-154">Create an Microsoft 365 group in the admin center</span></span>](../admin/create-groups/create-groups.md)