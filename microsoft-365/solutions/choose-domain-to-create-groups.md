---
title: Wählen Sie die Domäne aus, die beim Erstellen Microsoft 365 werden soll
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
recommendations: false
description: Erfahren Sie, wie Sie die Domäne auswählen, die beim Erstellen Microsoft 365 Gruppen verwendet werden soll, indem Sie E-Mail-Adressrichtlinien mithilfe von PowerShell konfigurieren.
ms.openlocfilehash: 4d620c3344f83f56afd05c00d78615331dd413ed
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583148"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="f088e-103">Wählen Sie die Domäne aus, die beim Erstellen Microsoft 365 werden soll</span><span class="sxs-lookup"><span data-stu-id="f088e-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="f088e-104">Einige Organisationen verwenden separate E-Mail-Domänen, um unterschiedliche Unternehmensbereiche zu segmentieren.</span><span class="sxs-lookup"><span data-stu-id="f088e-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="f088e-105">Sie können angeben, welche Domäne verwendet werden soll, wenn Ihre Benutzer Microsoft 365 erstellen.</span><span class="sxs-lookup"><span data-stu-id="f088e-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="f088e-106">Wenn Benutzer in Ihrer Organisation ihre Gruppen in anderen Domänen als der akzeptierten Standarddomäne Ihres Unternehmens erstellen müssen, können Sie dies erlauben, indem Sie E-Mail-Adressrichtlinien (Email Address Policies, EAPs) mithilfe von PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f088e-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="f088e-107">Bevor Sie die PowerShell-Cmdlets ausführen können, laden Sie ein Modul herunter, mit dem Sie mit Ihrer Organisation sprechen können.</span><span class="sxs-lookup"><span data-stu-id="f088e-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="f088e-108">Lesen Sie [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f088e-108">Check out [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="f088e-109">Beispielszenarien</span><span class="sxs-lookup"><span data-stu-id="f088e-109">Example scenarios</span></span>

<span data-ttu-id="f088e-110">Angenommen, die Hauptdomäne Ihres Unternehmens ist Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f088e-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="f088e-111">Die standardmäßig akzeptierte Domäne Ihrer Organisation ist jedoch service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f088e-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="f088e-112">Dies bedeutet, dass Gruppen in service.contoso.com erstellt werden (z. B. jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="f088e-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="f088e-113">Weiterhin angenommen, Sie haben in Ihrer Organisation auch Unterdomänen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="f088e-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="f088e-114">Sie möchten auch, dass Gruppen in diesen Domänen erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="f088e-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="f088e-115">students.contoso.com für Studierende</span><span class="sxs-lookup"><span data-stu-id="f088e-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="f088e-116">faculty.contoso.com für Lehrkräfte</span><span class="sxs-lookup"><span data-stu-id="f088e-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="f088e-117">Anhand der beiden folgenden Szenarien wird erläutert, wie Sie dies erreichen können.</span><span class="sxs-lookup"><span data-stu-id="f088e-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="f088e-118">Wenn Sie über Mulitple-EAPs verfügen, werden sie in der Reihenfolge ihrer Priorität ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="f088e-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="f088e-119">Der Wert 1 bedeutet die höchste Priorität.</span><span class="sxs-lookup"><span data-stu-id="f088e-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="f088e-120">Sobald ein EAP übereinstimmunget, wird keine weitere EAP ausgewertet, und Adressen, die für die Gruppe gestempelt werden, entsprechen dem übereinstimmenen EAP.</span><span class="sxs-lookup"><span data-stu-id="f088e-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="f088e-121">> Wenn keine EAPs den angegebenen Kriterien entsprechen, wird die Gruppe in der standardmäßig akzeptierten Domäne der Organisation bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f088e-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="f088e-122">Weitere Informationen zum Hinzufügen einer akzeptierten Domäne finden Sie [unter Manage accepted domains Exchange Online in](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f088e-122">Check out [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="f088e-123">Szenario 1</span><span class="sxs-lookup"><span data-stu-id="f088e-123">Scenario 1</span></span>

<span data-ttu-id="f088e-124">Das folgende Beispiel zeigt, wie Sie alle Microsoft 365 in Ihrer Organisation in der groups.contoso.com bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f088e-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="f088e-125">Szenario 2</span><span class="sxs-lookup"><span data-stu-id="f088e-125">Scenario 2</span></span>

<span data-ttu-id="f088e-126">Angenommen, Sie möchten steuern, in welchen Unterdomänen Microsoft 365 Gruppen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f088e-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="f088e-127">Du willst:</span><span class="sxs-lookup"><span data-stu-id="f088e-127">You want:</span></span>
  
- <span data-ttu-id="f088e-128">Von Kursteilnehmern erstellte Gruppen (Benutzer, für die **Abteilung** auf Kursteilnehmer **festgelegt** ist) in students.groups.contoso.com Domäne.</span><span class="sxs-lookup"><span data-stu-id="f088e-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="f088e-129">Verwenden Sie dazu diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="f088e-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="f088e-130">Von Lehrkräften erstellte Gruppen (Benutzer, deren **Abteilung** auf Fakultät oder E-Mail-Adresse festgelegt ist, enthält **faculty.contoso.com)** in der faculty.groups.contoso.com Domäne.</span><span class="sxs-lookup"><span data-stu-id="f088e-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="f088e-131">Verwenden Sie dazu diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="f088e-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="f088e-132">Gruppen, die von anderen Personen erstellt werden, werden in der groups.contoso.com erstellt.</span><span class="sxs-lookup"><span data-stu-id="f088e-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="f088e-133">Verwenden Sie dazu diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="f088e-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="f088e-134">Ändern von E-Mail-Adressrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f088e-134">Change email address policies</span></span>

<span data-ttu-id="f088e-135">Zum Ändern der Priorität oder von E-Mail-Adressvorlagen für eine vorhandene EAP verwenden Sie das Cmdlet "Set-EmailAddressPolicy".</span><span class="sxs-lookup"><span data-stu-id="f088e-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="f088e-136">Die Änderung einer EAP hat keine Auswirkungen auf die bereits bereitgestellten Gruppen.</span><span class="sxs-lookup"><span data-stu-id="f088e-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="f088e-137">Löschen von E-Mail-Adressrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f088e-137">Delete email address policies</span></span>

<span data-ttu-id="f088e-138">Zum Löschen einer EAP verwenden Sie das Cmdlet "Remove-EmailAddressPolicy".</span><span class="sxs-lookup"><span data-stu-id="f088e-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="f088e-139">Die Änderung einer EAP hat keine Auswirkungen auf die bereits bereitgestellten Gruppen.</span><span class="sxs-lookup"><span data-stu-id="f088e-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="f088e-140">Anforderungen für Hybridbereitstellungen</span><span class="sxs-lookup"><span data-stu-id="f088e-140">Hybrid requirements</span></span>

<span data-ttu-id="f088e-141">Wenn Ihre Organisation in einem Hybridszenario konfiguriert ist, lesen Sie [Configure Microsoft 365 groups with on-premises Exchange hybrid,](/exchange/hybrid-deployment/set-up-microsoft-365-groups) um sicherzustellen, dass Ihre Organisation die Anforderungen für das Erstellen von Microsoft 365 erfüllt.</span><span class="sxs-lookup"><span data-stu-id="f088e-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="f088e-142">Zusätzliche Informationen zur Verwendung von E-Mail-Adressrichtliniengruppen:</span><span class="sxs-lookup"><span data-stu-id="f088e-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="f088e-143">Es gibt ein paar weitere Punkte, die Sie wissen müssen:</span><span class="sxs-lookup"><span data-stu-id="f088e-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="f088e-144">Wie schnell Gruppen erstellt werden, ist von der Anzahl der in Ihrer Organisation konfigurierten EAPs abhängig.</span><span class="sxs-lookup"><span data-stu-id="f088e-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="f088e-145">Administratoren und Benutzer können domänen auch ändern, wenn sie Gruppen erstellen.</span><span class="sxs-lookup"><span data-stu-id="f088e-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="f088e-146">Die Gruppe der Benutzer wird mithilfe der bereits verfügbaren Standardabfragen (Benutzereigenschaften) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="f088e-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="f088e-147">Weitere Informationen [finden Sie unter Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span><span class="sxs-lookup"><span data-stu-id="f088e-147">Check out [Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="f088e-148">Wenn Sie keine EAPs für Gruppen konfigurieren, wird die akzeptierte Standarddomäne für die Gruppenerstellung ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="f088e-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="f088e-149">Wenn Sie eine akzeptierte Domäne entfernen möchten, müssen Sie zuerst die EAPs aktualisieren, andernfalls hat dies Auswirkungen auf die Gruppenbereitstellung.</span><span class="sxs-lookup"><span data-stu-id="f088e-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="f088e-150">Für eine Organisation können maximal 100 E-Mail-Adressrichtlinien konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f088e-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-content"></a><span data-ttu-id="f088e-151">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="f088e-151">Related content</span></span>

<span data-ttu-id="f088e-152">[Planung der Steuerung der Zusammenarbeit schritt-für-Schritt](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="f088e-152">[Collaboration governance planning step-by-step](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step) (article)</span></span>

<span data-ttu-id="f088e-153">[Erstellen Ihres Governanceplans für die Zusammenarbeit](collaboration-governance-first.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="f088e-153">[Create your collaboration governance plan](collaboration-governance-first.md) (article)</span></span>

<span data-ttu-id="f088e-154">[Erstellen einer Microsoft 365 im Admin Center](../admin/create-groups/create-groups.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="f088e-154">[Create an Microsoft 365 group in the admin center](../admin/create-groups/create-groups.md) (article)</span></span>