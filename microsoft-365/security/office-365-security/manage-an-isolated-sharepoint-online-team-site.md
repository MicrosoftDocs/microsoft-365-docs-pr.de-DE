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
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Verwalten sie eine isolierte SharePoint Online-Teamwebsite, fügen Sie neue Benutzer und Gruppen hinzu, entfernen Sie Benutzer und Gruppen, und erstellen Sie einen Dokumentunterordner mit benutzerdefinierten Berechtigungen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 20e354de77b70ea69d69e201bd3b1d40ea32cc5b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289521"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="566f2-103">Verwalten einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="566f2-103">Manage an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="566f2-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="566f2-104">**Applies to**</span></span>
- [<span data-ttu-id="566f2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="566f2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="566f2-106">Microsoft Defender für Office 365 Plan 1</span><span class="sxs-lookup"><span data-stu-id="566f2-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="566f2-107">Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="566f2-107">SharePoint Online</span></span> 

 <span data-ttu-id="566f2-108">**Zusammenfassung:** Mit diesen Verfahren können Sie Ihre isolierte SharePoint Online-Teamwebsite verwalten.</span><span class="sxs-lookup"><span data-stu-id="566f2-108">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>

<span data-ttu-id="566f2-109">In diesem Artikel werden allgemeine Verwaltungsaufgaben für eine isolierte SharePoint Online-Teamwebsite erläutert.</span><span class="sxs-lookup"><span data-stu-id="566f2-109">This article describes common management operations for an isolated SharePoint Online team site.</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="566f2-110">Hinzufügen eines neuen Benutzers</span><span class="sxs-lookup"><span data-stu-id="566f2-110">Add a new user</span></span>

<span data-ttu-id="566f2-111">Wenn ein neuer Benutzer der Website beitritt, müssen Sie entscheiden, in welchem Umfang, d. h. mit welcher Berechtigungsstufe, er an der Website teilnehmen soll:</span><span class="sxs-lookup"><span data-stu-id="566f2-111">When someone new joins the site, you must decide their level of participation in the site:</span></span>

- <span data-ttu-id="566f2-112">Verwaltung: Fügen Sie das neue Benutzerkonto zur Zugriffsgruppe der Websiteadministratoren hinzu.</span><span class="sxs-lookup"><span data-stu-id="566f2-112">Administration: Add the new user account to the site admins access group</span></span>

- <span data-ttu-id="566f2-113">Aktive Zusammenarbeit: Fügen Sie das Benutzerkonto zur Zugriffsgruppe der Websitemitglieder hinzu.</span><span class="sxs-lookup"><span data-stu-id="566f2-113">Active collaboration: Add the user account to the site members access group</span></span>

- <span data-ttu-id="566f2-114">Anzeige: Fügen Sie das Benutzerkonto zur Zugriffsgruppe der Websitebetrachter hinzu.</span><span class="sxs-lookup"><span data-stu-id="566f2-114">Viewing: Add the user account to the site viewers access group</span></span>

<span data-ttu-id="566f2-115">Wenn Sie Benutzerkonten und Gruppen über Active Directory Domain Services (AD DS) verwalten, fügen Sie die entsprechenden Benutzer mithilfe Ihrer normalen AD DS-Benutzer- und Gruppenverwaltungsverfahren den entsprechenden Zugriffsgruppen hinzu, und warten Sie auf die Synchronisierung mit Ihrem Abonnement.</span><span class="sxs-lookup"><span data-stu-id="566f2-115">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="566f2-116">Wenn Sie Benutzerkonten und Gruppen über Microsoft 365 verwalten, können Sie das Microsoft 365 Admin Center oder Microsoft PowerShell verwenden:</span><span class="sxs-lookup"><span data-stu-id="566f2-116">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>

- <span data-ttu-id="566f2-117">Melden Sie sich im Microsoft 365 Admin Center mit einem Benutzerkonto an, dem die Rolle "Benutzerkontoadministrator" oder "Unternehmensadministrator" zugewiesen wurde, und verwenden Sie Gruppen, um die entsprechenden Benutzer den entsprechenden Zugriffsgruppen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="566f2-117">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>

- <span data-ttu-id="566f2-118">Stellen Sie für PowerShell zunächst eine Verbindung mit dem [Azure Active Directory PowerShell für Graph-Modul.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="566f2-118">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="566f2-119">Verwenden Sie den folgenden PowerShell-Befehlsblock, um ein Benutzerkonto unter Verwendung des Benutzerprinzipalnamens (User Principal Name, UPN) zu einer Zugriffsgruppe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="566f2-119">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="566f2-120">Verwenden Sie den folgenden PowerShell-Befehlsblock, um ein Benutzerkonto unter Verwendung des Anzeigenamens zu einer Zugriffsgruppe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="566f2-120">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="566f2-121">Hinzufügen einer neuen Gruppe</span><span class="sxs-lookup"><span data-stu-id="566f2-121">Add a new group</span></span>

<span data-ttu-id="566f2-122">Wenn Sie Zugriff für eine ganze Gruppe hinzufügen möchten, müssen Sie entscheiden, in welchem Umfang, d. h. mit welcher Berechtigungsstufe, sämtliche Mitglieder der Gruppe an der Website teilnehmen sollen:</span><span class="sxs-lookup"><span data-stu-id="566f2-122">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>

- <span data-ttu-id="566f2-123">Verwaltung: Fügen Sie die Gruppe zur Zugriffsgruppe der Websiteadministratoren hinzu.</span><span class="sxs-lookup"><span data-stu-id="566f2-123">Administration: Add the group to the site admins access group</span></span>

- <span data-ttu-id="566f2-124">Aktive Zusammenarbeit: Fügen Sie die Gruppe zur Zugriffsgruppe der Websitemitglieder hinzu.</span><span class="sxs-lookup"><span data-stu-id="566f2-124">Active collaboration: Add the group to the site members access group</span></span>

- <span data-ttu-id="566f2-125">Anzeige: Fügen Sie die Gruppe zur Zugriffsgruppe der Websitbetrachter hinzu.</span><span class="sxs-lookup"><span data-stu-id="566f2-125">Viewing: Add the group to the site viewers access group</span></span>

<span data-ttu-id="566f2-126">Wenn Sie Benutzerkonten und Gruppen über AD DS verwalten, fügen Sie die entsprechenden Gruppen mithilfe Ihrer normalen AD DS-Benutzer- und Gruppenverwaltungsverfahren den entsprechenden Gruppen hinzu, und warten Sie auf die Synchronisierung mit Ihrem Abonnement.</span><span class="sxs-lookup"><span data-stu-id="566f2-126">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="566f2-127">Wenn Sie Benutzerkonten und Gruppen über Office 365 verwalten, können Sie das Microsoft 365 Admin Center oder PowerShell verwenden:</span><span class="sxs-lookup"><span data-stu-id="566f2-127">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="566f2-128">Melden Sie sich im Microsoft 365 Admin Center mit einem Benutzerkonto an, dem die Rolle "Benutzerkontoadministrator" oder "Unternehmensadministrator" zugewiesen wurde, und verwenden Sie Gruppen, um die entsprechenden Gruppen den entsprechenden Zugriffsgruppen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="566f2-128">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>

- <span data-ttu-id="566f2-129">Stellen Sie für PowerShell zunächst eine Verbindung mit dem [Azure Active Directory PowerShell für Graph-Modul.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="566f2-129">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="566f2-130">Führen Sie dann die folgenden PowerShell-Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="566f2-130">Then, use the following PowerShell commands:</span></span>

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="566f2-131">Entfernen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="566f2-131">Remove a user</span></span>

<span data-ttu-id="566f2-132">Wenn der Zugriff auf eine Website für einen Benutzer entfernt werden muss, entfernen Sie den betreffenden Benutzer aus der Zugriffsgruppe, in der er derzeit basierend auf dem Umfang seiner Teilnahme an der Website Mitglied ist:</span><span class="sxs-lookup"><span data-stu-id="566f2-132">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="566f2-133">Verwaltung: Entfernen Sie das Benutzerkonto aus der Zugriffsgruppe der Websiteadministratoren.</span><span class="sxs-lookup"><span data-stu-id="566f2-133">Administration: Remove the user account from the site admins access group</span></span>

- <span data-ttu-id="566f2-134">Aktive Zusammenarbeit: Entfernen Sie das Benutzerkonto aus der Zugriffsgruppe der Websitemitglieder.</span><span class="sxs-lookup"><span data-stu-id="566f2-134">Active collaboration: Remove the user account from the site members access group</span></span>

- <span data-ttu-id="566f2-135">Anzeige: Entfernen Sie das Benutzerkonto aus der Zugriffsgruppe der Websitebetrachter.</span><span class="sxs-lookup"><span data-stu-id="566f2-135">Viewing: Remove the user account from the site viewers access group</span></span>

<span data-ttu-id="566f2-136">Wenn Sie Benutzerkonten und Gruppen über AD DS verwalten, entfernen Sie die entsprechenden Benutzer mithilfe Ihrer normalen AD DS-Benutzer- und Gruppenverwaltungsverfahren aus den entsprechenden Zugriffsgruppen, und warten Sie auf die Synchronisierung mit Ihrem Abonnement.</span><span class="sxs-lookup"><span data-stu-id="566f2-136">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="566f2-137">Wenn Sie Benutzerkonten und Gruppen über Office 365 verwalten, können Sie das Microsoft 365 Admin Center oder PowerShell verwenden:</span><span class="sxs-lookup"><span data-stu-id="566f2-137">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="566f2-138">Melden Sie sich im Microsoft 365 Admin Center mit einem Benutzerkonto an, dem die Rolle "Benutzerkontoadministrator" oder "Unternehmensadministrator" zugewiesen wurde, und verwenden Sie Gruppen, um die entsprechenden Benutzer aus den entsprechenden Zugriffsgruppen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="566f2-138">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>

- <span data-ttu-id="566f2-139">Stellen Sie für PowerShell zunächst eine Verbindung mit dem [Azure Active Directory PowerShell für Graph-Modul.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="566f2-139">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="566f2-140">Verwenden Sie den folgenden PowerShell-Befehlsblock, um ein Benutzerkonto unter Verwendung des UPN aus einer Zugriffsgruppe zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="566f2-140">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="566f2-141">Verwenden Sie den folgenden PowerShell-Befehlsblock, um ein Benutzerkonto unter Verwendung des Anzeigenamens aus einer Zugriffsgruppe zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="566f2-141">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="566f2-142">Entfernen einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="566f2-142">Remove a group</span></span>

<span data-ttu-id="566f2-143">Wenn der Zugriff für eine ganze Gruppe entfernt werden soll, entfernen Sie die betreffende Gruppe aus der Zugriffsgruppe, in der sie derzeit basierend auf dem Umfang ihrer Teilnahme an der Website Mitglied ist:</span><span class="sxs-lookup"><span data-stu-id="566f2-143">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="566f2-144">Verwaltung: Entfernen Sie die Gruppe aus der Zugriffsgruppe der Websiteadministratoren.</span><span class="sxs-lookup"><span data-stu-id="566f2-144">Administration: Remove the group from the site admins access group</span></span>

- <span data-ttu-id="566f2-145">Aktive Zusammenarbeit: Entfernen Sie die Gruppe aus der Zugriffsgruppe der Websitemitglieder.</span><span class="sxs-lookup"><span data-stu-id="566f2-145">Active collaboration: Remove the group from the site members access group</span></span>

- <span data-ttu-id="566f2-146">Anzeige: Entfernen Sie die Gruppe aus der Zugriffsgruppe der Websitebetrachter.</span><span class="sxs-lookup"><span data-stu-id="566f2-146">Viewing: Remove the group from the site viewers access group</span></span>

<span data-ttu-id="566f2-147">Wenn Sie Benutzerkonten und Gruppen über Windows Server Active Directory verwalten, entfernen Sie die entsprechenden Gruppen mithilfe Ihrer normalen AD DS-Benutzer- und Gruppenverwaltungsverfahren aus den entsprechenden Zugriffsgruppen, und warten Sie auf die Synchronisierung mit Ihrem Abonnement.</span><span class="sxs-lookup"><span data-stu-id="566f2-147">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="566f2-148">Wenn Sie Benutzerkonten und Gruppen über Office 365 verwalten, können Sie das Microsoft 365 Admin Center oder PowerShell verwenden:</span><span class="sxs-lookup"><span data-stu-id="566f2-148">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="566f2-149">Melden Sie sich im Microsoft 365 Admin Center mit einem Benutzerkonto an, dem die Rolle "Benutzerkontoadministrator" oder "Unternehmensadministrator" zugewiesen wurde, und verwenden Sie Gruppen, um die entsprechenden Gruppen aus den entsprechenden Zugriffsgruppen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="566f2-149">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>

- <span data-ttu-id="566f2-150">Stellen Sie für PowerShell zunächst eine Verbindung mit dem [Azure Active Directory PowerShell für Graph-Modul.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="566f2-150">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="566f2-151">Verwenden Sie den folgenden PowerShell-Befehlsblock, um eine Gruppe unter Verwendung des Anzeigenamens aus einer Zugriffsgruppe zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="566f2-151">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="566f2-152">Erstellen eines Dokumentunterordners mit benutzerdefinierten Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="566f2-152">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="566f2-p105">In manchen Fällen benötigt eine Teilmenge der Personen, die innerhalb der isolierten Website arbeiten, einen privateren Ort für die Zusammenarbeit. Für SharePoint Online-Websites können Sie einen Unterordner im Dokumentordner der Website erstellen und benutzerdefinierte Berechtigungen zuweisen. Benutzer ohne Berechtigungen können den Unterordner nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="566f2-p105">In some cases, a subset of the people working within the isolated site need a more private place to collaborate. For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions. Those without permissions will not see the subfolder.</span></span>

<span data-ttu-id="566f2-156">Gehen Sie zum Erstellen eines Dokumentunterordners mit benutzerdefinierten Berechtigungen folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="566f2-156">To create a documents subfolder with custom permissions, do the following:</span></span>

1. <span data-ttu-id="566f2-157">Melden Sie sich bei einem Konto an, das Mitglied der Zugriffsgruppe der Administratoren für die Website ist.</span><span class="sxs-lookup"><span data-stu-id="566f2-157">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="566f2-158">Hilfe finden Sie unter [Where to sign in to Microsoft 365 (Wo kann ich mich bei Microsoft 365 anmelden?)](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="566f2-158">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="566f2-159">Wechseln Sie zu der isolierten Teamwebsite, und klicken Sie auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="566f2-159">Go to the isolated team site and click **Documents**.</span></span>

3. <span data-ttu-id="566f2-160">Navigieren Sie zu dem Ordner im Dokumentordner, der den Unterordner mit benutzerdefinierten Berechtigungen enthalten soll, erstellen Sie den Ordner, und öffnen Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="566f2-160">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>

4. <span data-ttu-id="566f2-161">Klicken Sie auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="566f2-161">Click **Share**.</span></span>

5. <span data-ttu-id="566f2-162">Klicken Sie auf **Freigegeben für > Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="566f2-162">Click **Shared with > Advanced**.</span></span>

6. <span data-ttu-id="566f2-163">Klicken Sie auf **Berechtigungsvererbung beenden**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="566f2-163">Click **Stop inheriting permissions**, and then click **OK**.</span></span>

7. <span data-ttu-id="566f2-164">Klicken Sie auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="566f2-164">Click **Share**.</span></span>

8. <span data-ttu-id="566f2-165">Klicken Sie auf **Freigegeben für > Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="566f2-165">Click **Shared with > Advanced**.</span></span>

9. <span data-ttu-id="566f2-166">Klicken Sie auf **Berechtigungen erteilen > Freigegeben für > Erweitert**.</span><span class="sxs-lookup"><span data-stu-id="566f2-166">Click **Grant Permissions > Shared with > Advanced**.</span></span>

10. <span data-ttu-id="566f2-167">Klicken Sie auf der Berechtigungsseite auf **Mitglieder von \<site name>** in der Liste.</span><span class="sxs-lookup"><span data-stu-id="566f2-167">On the permissions page, click **\<site name> Members in the list**.</span></span>

11. <span data-ttu-id="566f2-168">Aktivieren Sie auf der Seite **Mitglieder von \<site name>** das Kontrollkästchen neben der Zugriffsgruppe der Websitemitglieder, klicken Sie auf **Aktionen**, klicken Sie auf **Benutzer aus Gruppe entfernen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="566f2-168">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>

12. <span data-ttu-id="566f2-169">Um diesem Unterordner bestimmte Mitglieder hinzuzufügen, klicken Sie auf **Neu > Benutzer hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="566f2-169">To add specific members to this subfolder, click **New > Add users**.</span></span>

13. <span data-ttu-id="566f2-170">Geben Sie im Dialogfeld **Freigeben** die Namen der Benutzerkonten ein, die an Dateien im Unterordner zusammenarbeiten können, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="566f2-170">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>

14. <span data-ttu-id="566f2-171">Aktualisieren Sie die Webseite, um die neuen Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="566f2-171">Refresh the web page to see the new results.</span></span>

15. <span data-ttu-id="566f2-172">Klicken Sie im linken Navigationsbereich unter **Gruppen** auf die Gruppe **Besucher von \<site name>**, und führen Sie die Schritte 11 bis 14 aus, um den Satz der Benutzerkonten anzugeben, die die Dateien im Unterordner anzeigen können (nach Bedarf).</span><span class="sxs-lookup"><span data-stu-id="566f2-172">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>

16. <span data-ttu-id="566f2-173">Klicken Sie im linken Navigationsbereich unter **Gruppen** auf die Gruppe **Besitzer von \<site name>**, und führen Sie die Schritte 11 bis 14 aus, um den Satz der Benutzerkonten anzugeben, die die Berechtigungen im Unterordner verwalten können (nach Bedarf).</span><span class="sxs-lookup"><span data-stu-id="566f2-173">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>

17. <span data-ttu-id="566f2-174">Schließen Sie die Registerkarte **Benutzer und Gruppen** im Browser.</span><span class="sxs-lookup"><span data-stu-id="566f2-174">Close the **People and Groups** tab in your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="566f2-175">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="566f2-175">See Also</span></span>

[<span data-ttu-id="566f2-176">Isolierte SharePoint Online-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="566f2-176">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="566f2-177">Entwerfen einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="566f2-177">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="566f2-178">Bereitstellen einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="566f2-178">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
