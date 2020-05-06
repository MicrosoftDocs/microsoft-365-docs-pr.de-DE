---
title: Verwalten einer isolierten SharePoint Online-Teamwebsite
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Verwalten einer isolierten SharePoint Online Teamwebsite, Hinzufügen neuer Benutzer und Gruppen, Entfernen von Benutzern und Gruppen und Erstellen eines Dokuments Unterordners mit benutzerdefinierten Berechtigungen.
ms.openlocfilehash: 05e3cf742482d34c158e14253eed9d1b99c82995
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036632"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="220fe-103">Verwalten einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="220fe-103">Manage an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="220fe-104">**Zusammenfassung:** Mit diesen Verfahren können Sie Ihre isolierte SharePoint Online-Teamwebsite verwalten.</span><span class="sxs-lookup"><span data-stu-id="220fe-104">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>
  
<span data-ttu-id="220fe-105">In diesem Artikel werden allgemeine Verwaltungsaufgaben für eine isolierte SharePoint Online-Teamwebsite erläutert.</span><span class="sxs-lookup"><span data-stu-id="220fe-105">This article describes common management operations for an isolated SharePoint Online team site.</span></span>
  
## <a name="add-a-new-user"></a><span data-ttu-id="220fe-106">Hinzufügen eines neuen Benutzers</span><span class="sxs-lookup"><span data-stu-id="220fe-106">Add a new user</span></span>

<span data-ttu-id="220fe-107">Wenn ein neuer Benutzer der Website beitritt, müssen Sie entscheiden, in welchem Umfang, d. h. mit welcher Berechtigungsstufe, er an der Website teilnehmen soll:</span><span class="sxs-lookup"><span data-stu-id="220fe-107">When someone new joins the site, you must decide their level of participation in the site:</span></span>
  
- <span data-ttu-id="220fe-108">Verwaltung: Fügen Sie das neue Benutzerkonto zur Zugriffsgruppe der Websiteadministratoren hinzu.</span><span class="sxs-lookup"><span data-stu-id="220fe-108">Administration: Add the new user account to the site admins access group</span></span>
    
- <span data-ttu-id="220fe-109">Aktive Zusammenarbeit: Fügen Sie das Benutzerkonto zur Zugriffsgruppe der Websitemitglieder hinzu.</span><span class="sxs-lookup"><span data-stu-id="220fe-109">Active collaboration: Add the user account to the site members access group</span></span>
    
- <span data-ttu-id="220fe-110">Anzeige: Fügen Sie das Benutzerkonto zur Zugriffsgruppe der Websitebetrachter hinzu.</span><span class="sxs-lookup"><span data-stu-id="220fe-110">Viewing: Add the user account to the site viewers access group</span></span>
    
<span data-ttu-id="220fe-111">Wenn Sie Benutzerkonten und Gruppen über Active Directory-Domänendienste (AD DS) verwalten, fügen Sie die entsprechenden Benutzer den entsprechenden Zugriffsgruppen mithilfe der normalen AD DS Benutzer-und Gruppen Verwaltungsverfahren hinzu, und warten Sie, bis die Synchronisierung mit Ihrem Abonnement erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="220fe-111">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="220fe-112">Wenn Sie Benutzerkonten und Gruppen über Microsoft 365 verwalten, können Sie das Microsoft 365 Admin Center oder Microsoft PowerShell verwenden:</span><span class="sxs-lookup"><span data-stu-id="220fe-112">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>
  
- <span data-ttu-id="220fe-113">Melden Sie sich für das Microsoft 365 Admin Center mit einem Benutzerkonto an, dem die Rolle "Benutzerkonto Administrator" oder "Unternehmensadministrator" zugewiesen wurde, und verwenden Sie Gruppen, um die entsprechenden Benutzer den entsprechenden Zugriffsgruppen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="220fe-113">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>
    
- <span data-ttu-id="220fe-114">Stellen Sie für PowerShell zunächst [eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul her](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="220fe-114">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="220fe-115">Verwenden Sie den folgenden PowerShell-Befehlsblock, um ein Benutzerkonto unter Verwendung des Benutzerprinzipalnamens (User Principal Name, UPN) zu einer Zugriffsgruppe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="220fe-115">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="220fe-116">Verwenden Sie den folgenden PowerShell-Befehlsblock, um ein Benutzerkonto unter Verwendung des Anzeigenamens zu einer Zugriffsgruppe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="220fe-116">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="220fe-117">Hinzufügen einer neuen Gruppe</span><span class="sxs-lookup"><span data-stu-id="220fe-117">Add a new group</span></span>

<span data-ttu-id="220fe-118">Wenn Sie Zugriff für eine ganze Gruppe hinzufügen möchten, müssen Sie entscheiden, in welchem Umfang, d. h. mit welcher Berechtigungsstufe, sämtliche Mitglieder der Gruppe an der Website teilnehmen sollen:</span><span class="sxs-lookup"><span data-stu-id="220fe-118">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>
  
- <span data-ttu-id="220fe-119">Verwaltung: Fügen Sie die Gruppe zur Zugriffsgruppe der Websiteadministratoren hinzu.</span><span class="sxs-lookup"><span data-stu-id="220fe-119">Administration: Add the group to the site admins access group</span></span>
    
- <span data-ttu-id="220fe-120">Aktive Zusammenarbeit: Fügen Sie die Gruppe zur Zugriffsgruppe der Websitemitglieder hinzu.</span><span class="sxs-lookup"><span data-stu-id="220fe-120">Active collaboration: Add the group to the site members access group</span></span>
    
- <span data-ttu-id="220fe-121">Anzeige: Fügen Sie die Gruppe zur Zugriffsgruppe der Websitbetrachter hinzu.</span><span class="sxs-lookup"><span data-stu-id="220fe-121">Viewing: Add the group to the site viewers access group</span></span>
    
<span data-ttu-id="220fe-122">Wenn Sie Benutzerkonten und Gruppen über AD DS verwalten, fügen Sie die entsprechenden Gruppen mithilfe der normalen AD DS Benutzer-und Gruppen Verwaltungsverfahren zu den entsprechenden Gruppen hinzu, und warten Sie, bis die Synchronisierung mit Ihrem Abonnement erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="220fe-122">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="220fe-123">Wenn Sie Benutzerkonten und Gruppen über Office 365 verwalten, können Sie das Microsoft 365 Admin Center oder PowerShell verwenden:</span><span class="sxs-lookup"><span data-stu-id="220fe-123">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="220fe-124">Melden Sie sich für das Microsoft 365 Admin Center mit einem Benutzerkonto an, dem die Rolle "Benutzerkonto Administrator" oder "Unternehmensadministrator" zugewiesen wurde, und verwenden Sie Gruppen zum Hinzufügen der entsprechenden Gruppen zu den entsprechenden Zugriffsgruppen.</span><span class="sxs-lookup"><span data-stu-id="220fe-124">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>
    
- <span data-ttu-id="220fe-125">Stellen Sie für PowerShell zunächst [eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul her](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="220fe-125">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="220fe-126">Führen Sie dann die folgenden PowerShell-Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="220fe-126">Then, use the following PowerShell commands:</span></span>
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="220fe-127">Entfernen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="220fe-127">Remove a user</span></span>

<span data-ttu-id="220fe-128">Wenn der Zugriff auf eine Website für einen Benutzer entfernt werden muss, entfernen Sie den betreffenden Benutzer aus der Zugriffsgruppe, in der er derzeit basierend auf dem Umfang seiner Teilnahme an der Website Mitglied ist:</span><span class="sxs-lookup"><span data-stu-id="220fe-128">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="220fe-129">Verwaltung: Entfernen Sie das Benutzerkonto aus der Zugriffsgruppe der Websiteadministratoren.</span><span class="sxs-lookup"><span data-stu-id="220fe-129">Administration: Remove the user account from the site admins access group</span></span>
    
- <span data-ttu-id="220fe-130">Aktive Zusammenarbeit: Entfernen Sie das Benutzerkonto aus der Zugriffsgruppe der Websitemitglieder.</span><span class="sxs-lookup"><span data-stu-id="220fe-130">Active collaboration: Remove the user account from the site members access group</span></span>
    
- <span data-ttu-id="220fe-131">Anzeige: Entfernen Sie das Benutzerkonto aus der Zugriffsgruppe der Websitebetrachter.</span><span class="sxs-lookup"><span data-stu-id="220fe-131">Viewing: Remove the user account from the site viewers access group</span></span>
    
<span data-ttu-id="220fe-132">Wenn Sie Benutzerkonten und Gruppen über AD DS verwalten, entfernen Sie die entsprechenden Benutzer aus den entsprechenden Zugriffsgruppen mithilfe ihrer normalen AD DS Benutzer-und Gruppen Verwaltungsverfahren, und warten Sie, bis die Synchronisierung mit Ihrem Abonnement erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="220fe-132">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="220fe-133">Wenn Sie Benutzerkonten und Gruppen über Office 365 verwalten, können Sie das Microsoft 365 Admin Center oder PowerShell verwenden:</span><span class="sxs-lookup"><span data-stu-id="220fe-133">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="220fe-134">Melden Sie sich für das Microsoft 365 Admin Center mit einem Benutzerkonto an, dem die Rolle "Benutzerkonto Administrator" oder "Unternehmensadministrator" zugewiesen wurde, und verwenden Sie Gruppen, um die entsprechenden Benutzer aus den entsprechenden Zugriffsgruppen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="220fe-134">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>
    
- <span data-ttu-id="220fe-135">Stellen Sie für PowerShell zunächst [eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul her](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="220fe-135">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="220fe-136">Verwenden Sie den folgenden PowerShell-Befehlsblock, um ein Benutzerkonto unter Verwendung des UPN aus einer Zugriffsgruppe zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="220fe-136">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="220fe-137">Verwenden Sie den folgenden PowerShell-Befehlsblock, um ein Benutzerkonto unter Verwendung des Anzeigenamens aus einer Zugriffsgruppe zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="220fe-137">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="220fe-138">Entfernen einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="220fe-138">Remove a group</span></span>

<span data-ttu-id="220fe-139">Wenn der Zugriff für eine ganze Gruppe entfernt werden soll, entfernen Sie die betreffende Gruppe aus der Zugriffsgruppe, in der sie derzeit basierend auf dem Umfang ihrer Teilnahme an der Website Mitglied ist:</span><span class="sxs-lookup"><span data-stu-id="220fe-139">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>
  
- <span data-ttu-id="220fe-140">Verwaltung: Entfernen Sie die Gruppe aus der Zugriffsgruppe der Websiteadministratoren.</span><span class="sxs-lookup"><span data-stu-id="220fe-140">Administration: Remove the group from the site admins access group</span></span>
    
- <span data-ttu-id="220fe-141">Aktive Zusammenarbeit: Entfernen Sie die Gruppe aus der Zugriffsgruppe der Websitemitglieder.</span><span class="sxs-lookup"><span data-stu-id="220fe-141">Active collaboration: Remove the group from the site members access group</span></span>
    
- <span data-ttu-id="220fe-142">Anzeige: Entfernen Sie die Gruppe aus der Zugriffsgruppe der Websitebetrachter.</span><span class="sxs-lookup"><span data-stu-id="220fe-142">Viewing: Remove the group from the site viewers access group</span></span>
    
<span data-ttu-id="220fe-143">Wenn Sie Benutzerkonten und Gruppen über Windows Server Active Directory verwalten, entfernen Sie die entsprechenden Gruppen aus den entsprechenden Zugriffsgruppen mithilfe ihrer normalen AD DS Benutzer-und Gruppen Verwaltungsverfahren, und warten Sie auf die Synchronisierung mit Ihrem Abonnement.</span><span class="sxs-lookup"><span data-stu-id="220fe-143">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>
  
<span data-ttu-id="220fe-144">Wenn Sie Benutzerkonten und Gruppen über Office 365 verwalten, können Sie das Microsoft 365 Admin Center oder PowerShell verwenden:</span><span class="sxs-lookup"><span data-stu-id="220fe-144">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>
  
- <span data-ttu-id="220fe-145">Melden Sie sich für das Microsoft 365 Admin Center mit einem Benutzerkonto an, dem die Rolle "Benutzerkonto Administrator" oder "Unternehmensadministrator" zugewiesen wurde, und verwenden Sie Gruppen, um die entsprechenden Gruppen aus den entsprechenden Zugriffsgruppen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="220fe-145">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>
    
- <span data-ttu-id="220fe-146">Stellen Sie für PowerShell zunächst [eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul her](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="220fe-146">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>    
<span data-ttu-id="220fe-147">Verwenden Sie den folgenden PowerShell-Befehlsblock, um eine Gruppe unter Verwendung des Anzeigenamens aus einer Zugriffsgruppe zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="220fe-147">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="220fe-148">Erstellen eines Dokumentunterordners mit benutzerdefinierten Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="220fe-148">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="220fe-p104">In manchen Fällen benötigt eine Teilmenge der Personen, die innerhalb der isolierten Website arbeiten, einen privateren Ort für die Zusammenarbeit. Für SharePoint Online-Websites können Sie einen Unterordner im Dokumentordner der Website erstellen und benutzerdefinierte Berechtigungen zuweisen. Benutzer ohne Berechtigungen können den Unterordner nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="220fe-p104">In some cases, a subset of the people working within the isolated site need a more private place to collaborate. For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions. Those without permissions will not see the subfolder.</span></span>
  
<span data-ttu-id="220fe-152">Gehen Sie zum Erstellen eines Dokumentunterordners mit benutzerdefinierten Berechtigungen folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="220fe-152">To create a documents subfolder with custom permissions, do the following:</span></span>
  
1. <span data-ttu-id="220fe-153">Melden Sie sich bei einem Konto an, das Mitglied der Zugriffsgruppe "Administratoren" für die Website ist.</span><span class="sxs-lookup"><span data-stu-id="220fe-153">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="220fe-154">Hilfe finden Sie unter [Where to sign in to Microsoft 365 (Wo kann ich mich bei Microsoft 365 anmelden?)](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="220fe-154">For help, see [Where to sign in to Microsoft 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="220fe-155">Wechseln Sie zu der isolierten Teamwebsite, und klicken Sie auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="220fe-155">Go to the isolated team site and click **Documents**.</span></span>
    
3. <span data-ttu-id="220fe-156">Navigieren Sie zu dem Ordner im Dokumentordner, der den Unterordner mit benutzerdefinierten Berechtigungen enthalten soll, erstellen Sie den Ordner, und öffnen Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="220fe-156">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>
    
4. <span data-ttu-id="220fe-157">Klicken Sie auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="220fe-157">Click **Share**.</span></span>
    
5. <span data-ttu-id="220fe-158">Klicken Sie auf **Freigegeben für > Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="220fe-158">Click **Shared with > Advanced**.</span></span>
    
6. <span data-ttu-id="220fe-159">Klicken Sie auf **Berechtigungsvererbung beenden**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="220fe-159">Click **Stop inheriting permissions**, and then click **OK**.</span></span>
    
7. <span data-ttu-id="220fe-160">Klicken Sie auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="220fe-160">Click **Share**.</span></span>
    
8. <span data-ttu-id="220fe-161">Klicken Sie auf **Freigegeben für > Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="220fe-161">Click **Shared with > Advanced**.</span></span>
    
9. <span data-ttu-id="220fe-162">Klicken Sie auf **Berechtigungen erteilen > Freigegeben für > Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="220fe-162">Click **Grant Permissions > Shared with > Advanced**.</span></span>
    
10. <span data-ttu-id="220fe-163">Klicken Sie auf der Berechtigungsseite auf **\<Mitglieder von Websitename>** in der Liste.
</span><span class="sxs-lookup"><span data-stu-id="220fe-163">On the permissions page, click **\<site name> Members in the list**.</span></span>
    
11. <span data-ttu-id="220fe-164">Aktivieren Sie auf der Seite **\<Mitglieder von Websitename** das Kontrollkästchen neben der Zugriffsgruppe der Websitemitglieder, klicken Sie auf **Aktionen**, klicken Sie auf **Benutzer aus Gruppe entfernen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="220fe-164">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>
    
12. <span data-ttu-id="220fe-165">Um diesem Unterordner bestimmte Mitglieder hinzuzufügen, klicken Sie auf **Neu > Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="220fe-165">To add specific members to this subfolder, click **New > Add users**.</span></span>
    
13. <span data-ttu-id="220fe-166">Geben Sie im Dialogfeld **Freigeben** die Namen der Benutzerkonten ein, die an Dateien im Unterordner zusammenarbeiten können, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="220fe-166">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>
    
14. <span data-ttu-id="220fe-167">Aktualisieren Sie die Webseite, um die neuen Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="220fe-167">Refresh the web page to see the new results.</span></span>
    
15. <span data-ttu-id="220fe-168">Klicken Sie im linken Navigationsbereich unter **Gruppen** auf die Gruppe Besucher von **\<Websitename**, und führen Sie die Schritte 11 bis 14 aus, um den Satz der Benutzerkonten anzugeben, die die Dateien im Unterordner anzeigen können (nach Bedarf).</span><span class="sxs-lookup"><span data-stu-id="220fe-168">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>
    
16. <span data-ttu-id="220fe-169">Klicken Sie im linken Navigationsbereich unter **Gruppen** auf die Gruppe **\<Besitzer von Websitename>**, und führen Sie die Schritte 11 bis 14 aus, um den Satz der Benutzerkonten anzugeben, die die Berechtigungen im Unterordner verwalten können (nach Bedarf).</span><span class="sxs-lookup"><span data-stu-id="220fe-169">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>
    
17. <span data-ttu-id="220fe-170">Schließen Sie die Registerkarte **Benutzer und Gruppen** im Browser.</span><span class="sxs-lookup"><span data-stu-id="220fe-170">Close the **People and Groups** tab in your browser.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="220fe-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="220fe-171">See Also</span></span>

[<span data-ttu-id="220fe-172">Isolierte SharePoint Online-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="220fe-172">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="220fe-173">Entwerfen einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="220fe-173">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="220fe-174">Bereitstellen einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="220fe-174">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)



