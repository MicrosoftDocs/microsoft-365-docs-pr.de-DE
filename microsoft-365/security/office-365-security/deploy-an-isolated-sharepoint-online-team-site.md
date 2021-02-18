---
title: Bereitstellen einer isolierten SharePoint Online-Teamwebsite
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: Verwenden Sie dieses schrittweise Bereitstellungshandbuch zum Erstellen und Konfigurieren einer isolierten SharePoint Online-Teamwebsite in Microsoft Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d226a545c3f8dc274f02e5d54d39739fe5d981ea
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288347"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="83438-103">Bereitstellen einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="83438-103">Deploy an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="83438-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="83438-104">**Applies to**</span></span>
- [<span data-ttu-id="83438-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="83438-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="83438-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83438-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

 <span data-ttu-id="83438-107">**Zusammenfassung:** Mithilfe dieser schrittweisen Anleitung können Sie eine neue isolierte SharePoint Online-Teamwebsite bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="83438-107">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>

<span data-ttu-id="83438-p101">Dieser Artikel ist eine schrittweises Bereitstellungshandbuch für das Erstellen und Konfigurieren einer isolierten SharePoint Online-Teamwebsite in Microsoft Office 365. Bei diesen Schritten wird die Verwendung der drei SharePoint-Standardgruppen und der entsprechenden Berechtigungsstufen vorausgesetzt, wobei für jede Zugriffsebene eine einzige Azure Active Directory (AD)-basierte Zugriffsgruppe vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="83438-p101">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365. These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>

## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="83438-110">Phase 1: Erstellen und Füllen der Zugriffsgruppen der Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="83438-110">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="83438-111">In dieser Phase erstellen Sie die drei Azure AD-basierten Zugriffsgruppen für die drei SharePoint-Standardgruppen und füllen sie mit den entsprechenden Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="83438-111">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="83438-p102">In den folgenden Schritte wird davon ausgegangen, dass alle erforderlichen Benutzerkonten bereits vorhanden und ihnen die entsprechenden Lizenzen zugewiesen sind. Wenn dies nicht der Fall ist, fügen Sie sie hinzu, und weisen Sie Lizenzen zu, bevor Sie mit Schritt 1 fortfahren.</span><span class="sxs-lookup"><span data-stu-id="83438-p102">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses. If not, please add them and assign licenses before proceeding to step 1.</span></span>

### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="83438-114">Schritt 1: Auflisten der SharePoint Online-Administratoren für die Website</span><span class="sxs-lookup"><span data-stu-id="83438-114">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="83438-115">Bestimmen Sie den Satz von Benutzerkonten, die den SharePoint Online-Administratoren für die isolierte Teamwebsite entsprechen.</span><span class="sxs-lookup"><span data-stu-id="83438-115">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>

<span data-ttu-id="83438-116">Wenn Sie Benutzerkonten und Gruppen über Microsoft 365 verwalten und Windows PowerShell verwenden möchten, erstellen Sie eine Liste ihrer Benutzerprinzipalnamen (UPNs) (Beispiel-UPN: belindan@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="83438-116">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>

### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="83438-117">Schritt 2: Auflisten der Mitglieder für die Website</span><span class="sxs-lookup"><span data-stu-id="83438-117">Step 2: List the members for the site</span></span>

<span data-ttu-id="83438-118">Bestimmen Sie den Satz von Benutzerkonten, die den Mitgliedern der isolierten Teamwebsite entsprechen, diejenigen, die an den in der Website gespeicherten Ressourcen zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="83438-118">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>

<span data-ttu-id="83438-119">Wenn Sie Benutzerkonten und Gruppen über Microsoft 365 verwalten und PowerShell verwenden möchten, erstellen Sie eine Liste ihrer UPNs.</span><span class="sxs-lookup"><span data-stu-id="83438-119">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="83438-120">Wenn die Website viele Mitglieder hat, können Sie die Liste der UPNs in einer Textdatei speichern und alle mit einem einzigen PowerShell-Befehl hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="83438-120">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="83438-121">Schritt 3: Auflisten der Betrachter für die Website</span><span class="sxs-lookup"><span data-stu-id="83438-121">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="83438-122">Bestimmen Sie den Satz von Benutzerkonten, die den Betrachtern der isolierten Teamwebsite entsprechen, diejenigen, die die auf der Website gespeicherten Ressourcen anzeigen, aber nicht ändern oder direkt an ihren Inhalten zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="83438-122">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>

<span data-ttu-id="83438-123">Wenn Sie Benutzerkonten und Gruppen über Microsoft 365 verwalten und PowerShell verwenden möchten, erstellen Sie eine Liste ihrer UPNs.</span><span class="sxs-lookup"><span data-stu-id="83438-123">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="83438-124">Wenn die Website viele Mitglieder hat, können Sie die Liste der UPNs in einer Textdatei speichern und alle mit einem einzigen PowerShell-Befehl hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="83438-124">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

<span data-ttu-id="83438-125">Zu den Betrachtern der Website können die Unternehmensführung, Rechtsberater oder Projektbeteiligte aus mehreren Abteilungen gehören.</span><span class="sxs-lookup"><span data-stu-id="83438-125">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>

### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="83438-126">Schritt 4: Erstellen der drei Zugriffsgruppen für die Website in Azure AD</span><span class="sxs-lookup"><span data-stu-id="83438-126">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="83438-127">Sie müssen die folgenden Zugriffsgruppen in Azure AD erstellen:</span><span class="sxs-lookup"><span data-stu-id="83438-127">You need to create the following access groups in Azure AD:</span></span>

- <span data-ttu-id="83438-128">Websiteadministratoren (umfassen die Liste aus Schritt 1)</span><span class="sxs-lookup"><span data-stu-id="83438-128">Site admins (which will contain the list from step 1)</span></span>
- <span data-ttu-id="83438-129">Websitemitglieder (umfassen die Liste aus Schritt 2)</span><span class="sxs-lookup"><span data-stu-id="83438-129">Site members (which will contain the list from step 2)</span></span>
- <span data-ttu-id="83438-130">Websitebetrachter (umfassen die Liste aus Schritt 3)</span><span class="sxs-lookup"><span data-stu-id="83438-130">Site viewers (which will contain the list from step 3)</span></span>

1. <span data-ttu-id="83438-131">Wechseln Sie in Ihrem Browser zum Azure-Portal unter <https://portal.azure.com>, und melden Sie sich mit den Anmeldeinformationen eines Kontos an, dem die Rolle „Unternehmensadministrator" oder „Benutzerverwaltungsadministrator" zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="83438-131">In your browser, go to the Azure portal at <https://portal.azure.com> and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>

2. <span data-ttu-id="83438-132">Klicken Sie im Azure-Portal auf **Azure Active Directory > Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="83438-132">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>

3. <span data-ttu-id="83438-133">Klicken Sie auf dem Blatt **Gruppen - Alle Gruppen** auf **+ Neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="83438-133">On the **Groups - All groups** blade, click **+ New group**.</span></span>

4. <span data-ttu-id="83438-134">Auf dem **Blatt "Neue Gruppe":**</span><span class="sxs-lookup"><span data-stu-id="83438-134">On the **New Group** blade:</span></span>

   - <span data-ttu-id="83438-135">Wählen Sie unter **Gruppentyp** die Option **Sicherheit** aus.</span><span class="sxs-lookup"><span data-stu-id="83438-135">Select **Security** in **Group type**.</span></span>

   - <span data-ttu-id="83438-136">Geben Sie den Gruppennamen unter **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="83438-136">Type the group name in **Name**.</span></span>

   - <span data-ttu-id="83438-137">Geben Sie unter **Gruppenbeschreibung** eine Beschreibung der Gruppe ein.</span><span class="sxs-lookup"><span data-stu-id="83438-137">Type a description of the group in **Group description**.</span></span>

   - <span data-ttu-id="83438-138">Wählen Sie **Zugewiesen** unter **Mitgliedschaftstyp** aus.</span><span class="sxs-lookup"><span data-stu-id="83438-138">Select **Assigned** in **Membership type**.</span></span>

5. <span data-ttu-id="83438-139">Klicken Sie auf **Erstellen**, und schließen Sie dann das Blatt **Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="83438-139">Click **Create**, and then close the **Group** blade.</span></span>

6. <span data-ttu-id="83438-140">Wiederholen Sie die Schritte 3 bis 5 für weitere Gruppen.</span><span class="sxs-lookup"><span data-stu-id="83438-140">Repeat steps 3-5 for your additional groups.</span></span>

> [!NOTE]
> <span data-ttu-id="83438-141">Sie müssen das Azure-Portal verwenden, um die Gruppen zu erstellen, damit die Office-Features für diese aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="83438-141">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="83438-142">Wenn eine isolierte SharePoint Online-Website später als streng vertrauliche Website mit einer Azure Information Protection-Bezeichnung konfiguriert wird, um Dateien zu verschlüsseln und bestimmten Gruppen Berechtigungen zu erteilen, müssen die zulässigen Gruppen mit aktivierten Office-Features erstellt worden sein.</span><span class="sxs-lookup"><span data-stu-id="83438-142">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="83438-143">Sie können die Einstellung für Office-Features einer Azure Active Directory-Gruppe nicht mehr ändern, nachdem sie erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="83438-143">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span>

<span data-ttu-id="83438-144">Hier ist die resultierende Konfiguration mit den drei Websitezugriffsgruppen.</span><span class="sxs-lookup"><span data-stu-id="83438-144">Here is your resulting configuration with the three site access groups.</span></span>

![Die drei Zugriffsgruppen für die Bereitstellung einer isolierten SharePoint Online-Website.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)

### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="83438-p106">Schritt 5: Hinzufügen der Benutzerkonten zu den Zugriffsgruppen</span><span class="sxs-lookup"><span data-stu-id="83438-p106">Step 5. Add the user accounts to the access groups</span></span>

<span data-ttu-id="83438-148">Führen Sie in diesem Schritt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="83438-148">In this step, do the following:</span></span>

1. <span data-ttu-id="83438-149">Fügen Sie die Liste der Benutzer aus Schritt 1 der Zugriffsgruppe der Websiteadministratoren hinzu.</span><span class="sxs-lookup"><span data-stu-id="83438-149">Add the list of users from step 1 to the site admins access group.</span></span>
2. <span data-ttu-id="83438-150">Fügen Sie die Liste der Benutzer aus Schritt 2 der Zugriffsgruppe der Websitemitglieder hinzu.</span><span class="sxs-lookup"><span data-stu-id="83438-150">Add the list of users from step 2 to the site members access group.</span></span>
3. <span data-ttu-id="83438-151">Fügen Sie die Liste der Benutzer aus Schritt 3 der Zugriffsgruppe der Websitebetrachter hinzu.</span><span class="sxs-lookup"><span data-stu-id="83438-151">Add the list of users from step 3 to the site viewers access group.</span></span>

<span data-ttu-id="83438-152">Wenn Sie Benutzerkonten und Gruppen über Active Directory Domain Services (AD DS) verwalten, fügen Sie Benutzer mithilfe Ihrer normalen AD DS-Benutzer- und Gruppenverwaltungsverfahren zu den entsprechenden Zugriffsgruppen hinzu, und warten Sie auf die Synchronisierung mit Ihrem Microsoft 365-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="83438-152">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>

<span data-ttu-id="83438-153">Wenn Sie Benutzerkonten und Gruppen über Office 365 verwalten, können Sie das Microsoft 365 Admin Center oder PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="83438-153">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="83438-154">Wenn Sie doppelte Gruppennamen für eine der Zugriffsgruppen haben, sollten Sie das Microsoft 365 Admin Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="83438-154">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>

<span data-ttu-id="83438-155">Melden Sie sich im Microsoft 365 Admin Center mit einem Benutzerkonto an, dem die Rolle "Benutzerkontoadministrator" oder "Unternehmensadministrator" zugewiesen wurde, und verwenden Sie Gruppen, um die entsprechenden Benutzerkonten und Gruppen den entsprechenden Zugriffsgruppen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="83438-155">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>

<span data-ttu-id="83438-156">Stellen Sie für PowerShell zunächst eine Verbindung mit dem [Azure Active Directory PowerShell für Graph-Modul.](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="83438-156">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="83438-157">Verwenden Sie dann den folgenden Befehlsblock, um ein einzelnes Benutzerkonto zu einer Zugriffsgruppe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="83438-157">Next, use the following command block to add an individual user account to an access group:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="83438-158">Wenn Sie die UPNs von Benutzerkonten für eine der Zugriffsgruppen in einer Textdatei gespeichert haben, können Sie den folgenden PowerShell-Befehlsblock verwenden, um alle gleichzeitig hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="83438-158">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>

```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="83438-159">Verwenden Sie bei Verwendung von PowerShell den folgenden Befehlsblock, um eine einzelne Gruppe zu einer Zugriffsgruppe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="83438-159">For PowerShell, use the following command block to add an individual group to an access group:</span></span>

```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="83438-160">Die Ergebnisse sollten folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="83438-160">The results should be the following:</span></span>

- <span data-ttu-id="83438-161">Die Azure AD-Gruppe der Websiteadministratoren enthält die Benutzerkonten und -gruppen der Websiteadministratoren.</span><span class="sxs-lookup"><span data-stu-id="83438-161">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
- <span data-ttu-id="83438-162">Die Azure AD-Gruppe der Websitemitglieder enthält die Benutzerkonten und -gruppen der Websitemitglieder.</span><span class="sxs-lookup"><span data-stu-id="83438-162">The site members Azure AD group contains the site member user accounts or groups</span></span>
- <span data-ttu-id="83438-163">Die Azure AD-Gruppe der Websitebetrachter enthält die Benutzerkonten oder -gruppen, die den Websiteinhalt lediglich anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="83438-163">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>

<span data-ttu-id="83438-164">Überprüfen Sie die Liste der Gruppenmitglieder für jede Zugriffsgruppe mit dem Microsoft 365 Admin Center oder mit dem folgenden PowerShell-Befehlsblock:</span><span class="sxs-lookup"><span data-stu-id="83438-164">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>

```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="83438-165">Hier ist die resultierende Konfiguration mit den drei Websitezugriffsgruppen mit Benutzerkonten und -gruppen.</span><span class="sxs-lookup"><span data-stu-id="83438-165">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>

![Die drei Zugriffsgruppen, mit Benutzerkonten ausgefüllt.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)

## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="83438-167">Phase 2: Erstellen und Konfigurieren der isolierten Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="83438-167">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="83438-168">In dieser Phase erstellen Sie die isolierte SharePoint Online-Website und konfigurieren die Berechtigungen für die SharePoint Online-Standardberechtigungsstufen zur Verwendung der neuen Azure AD-basierten Zugriffsgruppen.</span><span class="sxs-lookup"><span data-stu-id="83438-168">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="83438-169">Standardmäßig enthalten neue Teamwebsites eine Microsoft 365-Gruppe und andere verwandte Ressourcen, aber in diesem Fall erstellen wir eine Teamwebsite ohne Microsoft 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="83438-169">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="83438-170">Dadurch können Berechtigungen vollständig über SharePoint beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="83438-170">This allows maintaining permissions entirely through SharePoint.</span></span>

<span data-ttu-id="83438-171">Erstellen Sie zuerst mit den folgenden Schritten die SharePoint Online-Teamwebsite.</span><span class="sxs-lookup"><span data-stu-id="83438-171">First, create the SharePoint Online team site with these steps.</span></span>

1. <span data-ttu-id="83438-172">Melden Sie sich beim Microsoft 365 Admin Center mit einem Konto an, das auch zum Verwalten der SharePoint Online-Teamwebsite (ein SharePoint Online-Administrator) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="83438-172">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="83438-173">Hilfe finden Sie unter [Where to sign in to Office 365 (Wo kann ich mich bei Office 365 anmelden?)](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="83438-173">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="83438-174">Klicken Sie im Microsoft 365 Admin Center unter **Admin Center** auf **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="83438-174">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="83438-175">Erweitern Sie im SharePoint Admin Center Websites, **und** klicken Sie auf **"Aktive Websites".**</span><span class="sxs-lookup"><span data-stu-id="83438-175">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="83438-176">Klicken **Sie auf**"Erstellen", und wählen Sie dann **"Andere Optionen" aus.**</span><span class="sxs-lookup"><span data-stu-id="83438-176">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="83438-177">Wählen Sie **in der Vorlagenliste** "Vorlage auswählen" die **Option "Teamwebsite" aus.**</span><span class="sxs-lookup"><span data-stu-id="83438-177">In the **Choose a template** list, choose **Team site**.</span></span>

6. <span data-ttu-id="83438-178">Geben Sie unter **Websitename** einen Namen für die Teamwebsite ein.</span><span class="sxs-lookup"><span data-stu-id="83438-178">In **Site name**, type a name for the team site.</span></span>

7. <span data-ttu-id="83438-179">Geben **Sie im primären** Administrator das Konto ein, mit dem Sie angemeldet sind.</span><span class="sxs-lookup"><span data-stu-id="83438-179">In **Primary administrator**, type the account that you are logged in with.</span></span>

8. <span data-ttu-id="83438-180">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="83438-180">Click **Finish**.</span></span>

<span data-ttu-id="83438-181">Konfigurieren Sie als Nächstes auf der neuen SharePoint Online-Teamwebsite die gewünschten Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="83438-181">Next, from the new SharePoint Online team site, configure permissions.</span></span>

1. <span data-ttu-id="83438-182">Klicken Sie in der Symbolleiste auf das Symbol „Einstellungen“ und anschließend auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="83438-182">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="83438-183">Klicken **Sie unter "Websitefreigabe"** **auf "Ändern, wie Mitglieder freigeben können".**</span><span class="sxs-lookup"><span data-stu-id="83438-183">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="83438-184">Wählen Sie **die Option "Nur Websitebesitzer können Dateien, Ordner und die Website freigeben" aus.**</span><span class="sxs-lookup"><span data-stu-id="83438-184">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="83438-185">Legen Sie **Zugriffsanforderungen auf "Zulassen"** auf **"Aus" festgelegt.**</span><span class="sxs-lookup"><span data-stu-id="83438-185">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="83438-186">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="83438-186">Click **Save**.</span></span>

6. <span data-ttu-id="83438-187">Klicken Sie **im Bereich "Berechtigungen"** auf **"Erweiterte Berechtigungseinstellungen".**</span><span class="sxs-lookup"><span data-stu-id="83438-187">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>

7. <span data-ttu-id="83438-188">Klicken Sie **auf** der Registerkarte "Berechtigungen" in Ihrem Browser auf **\<site name> "Mitglieder"** in der Liste.</span><span class="sxs-lookup"><span data-stu-id="83438-188">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>

8. <span data-ttu-id="83438-189">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="83438-189">In **People and Groups**, click **New**.</span></span>

9. <span data-ttu-id="83438-190">Geben Sie im Dialogfeld **Freigeben** den Namen der Zugriffsgruppe der Websitemitglieder ein, wählen Sie ihn aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="83438-190">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>

10. <span data-ttu-id="83438-191">Klicken Sie auf die Schaltfläche „Zurück“ in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="83438-191">Click the back button on your browser.</span></span>

11. <span data-ttu-id="83438-192">Klicken **\<site name> Sie** in der Liste auf "Besitzer".</span><span class="sxs-lookup"><span data-stu-id="83438-192">Click **\<site name> Owners** in the list.</span></span>

12. <span data-ttu-id="83438-193">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="83438-193">In **People and Groups**, click **New**.</span></span>

13. <span data-ttu-id="83438-194">Geben Sie im Dialogfeld **Freigeben** den Namen der Zugriffsgruppe der Websiteadministratoren ein, wählen Sie ihn aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="83438-194">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="83438-195">Klicken Sie auf die Schaltfläche „Zurück“ in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="83438-195">Click the back button on your browser.</span></span>

15. <span data-ttu-id="83438-196">Klicken Sie in **\<site name> der** Liste auf "Besucher".</span><span class="sxs-lookup"><span data-stu-id="83438-196">Click **\<site name> Visitors** in the list.</span></span>

16. <span data-ttu-id="83438-197">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="83438-197">In **People and Groups**, click **New**.</span></span>

17. <span data-ttu-id="83438-198">Geben Sie im Dialogfeld **Freigeben** den Namen der Zugriffsgruppe der Websitebetrachter ein, wählen Sie ihn aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="83438-198">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="83438-199">Schließen Sie die Registerkarte **Berechtigungen** Ihres Browsers.</span><span class="sxs-lookup"><span data-stu-id="83438-199">Close the **Permissions** tab of your browser.</span></span>

<span data-ttu-id="83438-200">Die Ergebnisse dieser Berechtigungseinstellungen sehen folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="83438-200">The results of these permission settings are:</span></span>

- <span data-ttu-id="83438-201">Die **\<site name> Besitzer-SharePoint-Gruppe** enthält die Zugriffsgruppe der Websiteadministratoren, in der alle Mitglieder über die Berechtigungsstufe **"Vollzugriff"** verfügen.</span><span class="sxs-lookup"><span data-stu-id="83438-201">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
- <span data-ttu-id="83438-202">Die **\<site name> Mitglieder-SharePoint-Gruppe** enthält die Zugriffsgruppe der Websitemitglieder, in der alle Mitglieder über die Berechtigungsstufe **"Bearbeiten"** verfügen.</span><span class="sxs-lookup"><span data-stu-id="83438-202">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
- <span data-ttu-id="83438-203">Die **\<site name> Besucher-SharePoint-Gruppe** enthält die Zugriffsgruppe der Websiteanzeigen, in der alle Mitglieder über die Berechtigungsstufe **"Lesen"** verfügen.</span><span class="sxs-lookup"><span data-stu-id="83438-203">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
- <span data-ttu-id="83438-204">Mitglieder können keine anderen Mitglieder einladen, und Nichtmitglieder können keinen Zugriff anfordern.</span><span class="sxs-lookup"><span data-stu-id="83438-204">The ability for members to invite other members or for non-members to request access is disabled.</span></span>

<span data-ttu-id="83438-205">Hier ist die resultierende Konfiguration mit den drei SharePoint-Gruppen für die Website, die für die Verwendung der Zugriffsgruppen konfiguriert ist, die mit Benutzerkonten oder Azure AD-Gruppen ausgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="83438-205">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>

![Die endgültige Konfiguration der isolierten SharePoint Online-Website mit Zugriffsgruppen und Benutzerkonten.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)

<span data-ttu-id="83438-207">Jetzt können Sie und die Mitglieder der Website über Gruppenmitgliedschaft in einer der Zugriffsgruppen zusammenarbeiten und die Ressourcen der Website nutzen.</span><span class="sxs-lookup"><span data-stu-id="83438-207">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>

## <a name="next-step"></a><span data-ttu-id="83438-208">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="83438-208">Next step</span></span>

<span data-ttu-id="83438-209">Wenn Sie die Website-Zugriffsgruppenmitgliedschaft ändern oder einen Dokumentordner mit benutzerdefinierten Berechtigungen erstellen müssen, finden Sie entsprechende Informationen unter [Verwalten einer isolierten SharePoint Online-Teamwebsite](manage-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="83438-209">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="83438-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83438-210">See Also</span></span>

[<span data-ttu-id="83438-211">Isolierte SharePoint Online-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="83438-211">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="83438-212">Entwerfen einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="83438-212">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="83438-213">Verwalten einer isolierten SharePoint Online-Teamwebsite</span><span class="sxs-lookup"><span data-stu-id="83438-213">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
