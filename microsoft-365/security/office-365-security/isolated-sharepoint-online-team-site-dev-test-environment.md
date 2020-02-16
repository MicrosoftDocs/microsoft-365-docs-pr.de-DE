---
title: Isolierte SharePoint Online-Teamwebsite in Ihrer Office 365-Entwicklungs-/Testumgebung
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
- TLG
- Ent_TLGs
ms.assetid: d1795031-beef-49ea-a6fc-5da5450d320d
description: 'Zusammenfassung: Konfigurieren einer SharePoint Online-Teamwebsite, die vom Rest der Organisation in Ihrer Office 365-Entwicklungs-/Testumgebung isoliert ist.'
ms.openlocfilehash: fc56a151d00eba3a6c0131ae1692febe69e76122
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083002"
---
# <a name="isolated-sharepoint-online-team-site-devtest-environment"></a><span data-ttu-id="bf1c5-103">Isolierte SharePoint Online-Teamwebsite in Ihrer Office 365-Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="bf1c5-103">Isolated SharePoint Online team site dev/test environment</span></span>

 <span data-ttu-id="bf1c5-104">**Zusammenfassung:** Konfigurieren einer SharePoint Online-Teamwebsite, die vom Rest der Organisation in Ihrer Office 365-Entwicklungs-/Testumgebung isoliert ist.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-104">**Summary:** Configure a SharePoint Online team site that is isolated from the rest of the organization in your Office 365 dev/test environment.</span></span>

<span data-ttu-id="bf1c5-p101">SharePoint Online-Teamwebsites in Office 365 sind Orte für die Zusammenarbeit unter Verwendung einer gemeinsamen Dokumentbibliothek, eines OneNote-Notizbuchs und anderer Dienste. In vielen Fällen sind ein umfangreicher Zugriff sowie eine ausgedehnte Zusammenarbeit über Abteilungen oder Organisationen hinweg hilfreich. In einigen Fällen ist es jedoch empfehlenswert, den Zugriff und die Berechtigungen für die Zusammenarbeit in einer kleinen Personengruppe genau zu steuern.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-p101">SharePoint Online team sites in Office 365 are locations for collaboration using a common document library, a OneNote notebook, and other services. In many cases, you want wide access and collaboration across departments or organizations. However, in some cases, you want to tightly control the access and permissions for collaboration among a small group of people.</span></span>

<span data-ttu-id="bf1c5-p102">Der Zugriff auf SharePoint Online-Teamwebsites und die Aktionen, die Benutzer ausführen können, werden durch SharePoint-Gruppen und Berechtigungsstufen gesteuert. SharePoint Online-Websites haben standardmäßig drei Zugriffsebenen:</span><span class="sxs-lookup"><span data-stu-id="bf1c5-p102">Access to SharePoint Online team sites and what users can do is controlled by SharePoint groups and permission levels. By default, SharePoint Online sites have three levels of access:</span></span>

- <span data-ttu-id="bf1c5-110">**Mitglieder**, die Ressourcen auf dieser Website anzeigen, erstellen und ändern können.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-110">**Members**, who can view, create, and modify resources on the site.</span></span>

- <span data-ttu-id="bf1c5-111">**Besitzer**, die über eine vollständige Kontrolle über die Website verfügen, einschließlich der Fähigkeit, Berechtigungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-111">**Owners**, who have complete control of the site, including the ability to change permissions.</span></span>

- <span data-ttu-id="bf1c5-112">**Besucher**, die Ressourcen auf der Website nur anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-112">**Visitors**, who only can view resources on the site.</span></span>

<span data-ttu-id="bf1c5-p103">In diesem Artikel werden Sie durch die Konfiguration einer isolierten SharePoint Online-Teamwebsite für ein geheimes Forschungsprojekt mit dem Namen „ProjectX“ geführt. Die Zugriffsanforderungen sehen folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="bf1c5-p103">This article steps you through the configuration of an isolated SharePoint Online team site for a secret research project named ProjectX. The access requirements are:</span></span>

- <span data-ttu-id="bf1c5-115">Nur Mitglieder des Projekts können auf die Website und deren Inhalte (Dokumente, OneNote-Notizbuch, Seiten) über SharePoint-Berechtigungsstufen zum Bearbeiten und Anzeigen zugreifen, die über die Gruppenmitgliedschaft gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-115">Only members of the project can access the site and its contents (documents, OneNote Notebook, Pages), with edit and view SharePoint permission levels controlled through group membership.</span></span>

- <span data-ttu-id="bf1c5-116">Nur der Ersteller der Website und die Mitglieder einer Administratorengruppe für die Website können die Websiteverwaltung durchführen, die das Ändern von Berechtigungen auf Websiteebene umfasst.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-116">Only the site creator and members of an Admins group for the site can perform site administration, which includes modifying site-level permissions.</span></span>

<span data-ttu-id="bf1c5-117">Das Einrichten einer isolierten SharePoint Online-Teamwebsite in Ihrer Office 365-Entwicklungs-/Testumgebung umfasst drei Phasen:</span><span class="sxs-lookup"><span data-stu-id="bf1c5-117">There are three phases to setting up an isolated SharePoint Online team site in your Office 365 dev/test environment:</span></span>

1. <span data-ttu-id="bf1c5-118">Erstellen der Office 365-Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="bf1c5-118">Create the Office 365 dev/test environment.</span></span>

2. <span data-ttu-id="bf1c5-119">Erstellen der Benutzer und Gruppen für ProjectX.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-119">Create the users and groups for ProjectX.</span></span>

3. <span data-ttu-id="bf1c5-120">Erstellen einer neuen SharePoint Online-Teamwebsite für ProjectX und Isolieren der Website.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-120">Create a new ProjectX SharePoint Online team site and isolate it.</span></span>

> [!TIP]
> <span data-ttu-id="bf1c5-121">Klicken Sie [hier](https://aka.ms/catlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in der One Microsoft Cloud zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-121">Click [here](https://aka.ms/catlgstack) for a visual map to all the articles in the One Microsoft Cloud Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-lightweight-or-simulated-enterprise-office-365-devtest-environment"></a><span data-ttu-id="bf1c5-122">Phase 1: Erstellen einer einfachen oder simulierten Office 365-Unternehmensentwicklungs-/-testumgebung</span><span class="sxs-lookup"><span data-stu-id="bf1c5-122">Phase 1: Build out your lightweight or simulated enterprise Office 365 dev/test environment</span></span>

<span data-ttu-id="bf1c5-123">Wenn Sie lediglich auf einfache Weise eine isolierte SharePoint Online-Teamwebsite mit den Mindestanforderungen erstellen möchten, befolgen Sie die Anweisungen in den Phasen 2 und 3 unter [Office 365-Entwicklungs-/Testumgebung](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span><span class="sxs-lookup"><span data-stu-id="bf1c5-123">If you just want to create an isolated SharePoint Online team site in a lightweight way with the minimum requirements, follow the instructions in phases 2 and 3 of [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span></span>

<span data-ttu-id="bf1c5-124">Wenn Sie eine isolierte SharePoint Online-Teamwebsite in einer simulierten Unternehmenskonfiguration erstellen möchten, befolgen Sie die Anweisungen unter [DirSync für die Office 365-Entwicklungs-/Testumgebung](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment).</span><span class="sxs-lookup"><span data-stu-id="bf1c5-124">If you want to create an isolated SharePoint Online team site in a simulated enterprise configuration, follow the instructions in [DirSync for your Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/dirsync-for-your-office-365-dev-test-environment).</span></span>

> [!NOTE]
> <span data-ttu-id="bf1c5-125">Für das Erstellen einer isolierten SharePoint Online Website ist keine simulierte Enterprise-Entwicklungs-/Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-125">Creating an isolated SharePoint Online site does not require the simulated enterprise dev/test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="bf1c5-126">Dies wird hier als Option bereitgestellt, damit Sie eine isolierte SharePoint Online-Website testen und damit in einer Umgebung, die eine typische Organisation darstellt, experimentieren können.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-126">It is provided here as an option so that you can test an isolated SharePoint Online site and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-user-accounts-and-access-groups"></a><span data-ttu-id="bf1c5-127">Phase 2: Erstellen von Benutzerkonten und Zugriffsgruppen</span><span class="sxs-lookup"><span data-stu-id="bf1c5-127">Phase 2: Create user accounts and access groups</span></span>

<span data-ttu-id="bf1c5-128">Befolgen Sie die Anweisungen unter [Verbinden mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell), um eine Verbindung zu Ihrem Office 365-Testabonnement über Ihr globales Administratorkonto von folgender Stelle aus herzustellen:</span><span class="sxs-lookup"><span data-stu-id="bf1c5-128">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) to connect to your Office 365 trail subscription with your global administrator account from:</span></span>

- <span data-ttu-id="bf1c5-129">Ihrem Computer aus (für die einfache Office 365-Entwicklungs-/Testunternehmensumgebung).</span><span class="sxs-lookup"><span data-stu-id="bf1c5-129">Your computer (for the lightweight Office 365 dev/test environment).</span></span>

- <span data-ttu-id="bf1c5-130">Dem virtuellen Computer CLIENT1 aus (für die simulierte Office 365-Entwicklungs-/Testumgebung).</span><span class="sxs-lookup"><span data-stu-id="bf1c5-130">The CLIENT1 virtual machine (for the simulated enterprise Office 365 dev/test environment).</span></span>

<span data-ttu-id="bf1c5-131">Führen Sie die folgenden Befehle aus dem Microsoft Azure Active Directory-Modul für Windows PowerShell aus, um die neuen Zugriffsgruppen für die SharePoint Online-Teamwebsite für ProjectX zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="bf1c5-131">To create the new access groups for the ProjectX SharePoint Online team site, run these commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$groupName="ProjectX-Members"
$groupDesc="People allowed to collaborate for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Admins"
$groupDesc="People allowed to administer SharePoint for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
$groupName="ProjectX-Viewers"
$groupDesc="People allowed to view the SharePoint resources for ProjectX."
New-MsolGroup -DisplayName $groupName -Description $groupDesc
```

<span data-ttu-id="bf1c5-132">Geben Sie den Namen Ihrer Organisation (z. B. „contosotoycompany“) und den zweistelligen Ländercode für Ihren Standort ein. Führen Sie dann über die Eingabeaufforderung des Windows Azure Active Directory-Moduls für Windows PowerShell die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="bf1c5-132">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, and then run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$licAssignment= $orgName + ":ENTERPRISEPREMIUM"
$userName= "designer@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Designer" -FirstName Lead -LastName Designer -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="bf1c5-133">Notieren Sie aus der **New-MsolUser** -Befehlsanzeige das Kennwort, das für das Lead Designer-Konto generiert wurde, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-133">From the display of the **New-MsolUser** command, note the generated password for the Lead Designer account and record it in a safe location.</span></span>

<span data-ttu-id="bf1c5-134">Führen Sie über die „Windows Azure Active Directory-Modul für Windows PowerShell“-Eingabeaufforderung die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="bf1c5-134">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "researcher@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Lead Researcher" -FirstName Lead -LastName Researcher -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="bf1c5-135">Notieren Sie aus der **New-MsolUser** -Befehlsanzeige das Kennwort, das für das Lead Researcher-Konto generiert wurde, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-135">From the display of the **New-MsolUser** command, note the generated password for the Lead Researcher account and record it in a safe location.</span></span>

<span data-ttu-id="bf1c5-136">Führen Sie über die „Windows Azure Active Directory-Modul für Windows PowerShell“-Eingabeaufforderung die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="bf1c5-136">Run the following commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$userName= "devvp@" + $orgName + ".onmicrosoft.com"
New-MsolUser -DisplayName "Development VP" -FirstName Development -LastName VP -UserPrincipalName $userName -UsageLocation $loc -LicenseAssignment $licAssignment -ForceChangePassword $false
```

<span data-ttu-id="bf1c5-137">Notieren Sie aus der **New-MsolUser** -Befehlsanzeige das Kennwort, das für das Development VP-Konto generiert wurde, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-137">From the display of the **New-MsolUser** command, note the generated password for the Development VP account and record it in a safe location.</span></span>

<span data-ttu-id="bf1c5-138">Führen Sie als Nächstes die folgenden PowerShell-Befehle aus dem Microsoft Azure Active Directory-Modul für Windows PowerShell aus, um die neuen Konten zu den neuen Zugriffsgruppen hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="bf1c5-138">Next, to add the new accounts to the new access groups, run these PowerShell commands from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>

```powershell
$grpName="ProjectX-Members"
$userUPN="designer@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$userUPN="researcher@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Admins"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userCredential.UserName }).ObjectID -GroupMemberType "User"
$grpName="ProjectX-Viewers"
$userUPN="devvp@" + $orgName + ".onmicrosoft.com"
Add-MsolGroupMember -GroupObjectId (Get-MsolGroup | Where { $_.DisplayName -eq $grpName }).ObjectID -GroupMemberObjectId (Get-MsolUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -GroupMemberType "User"
```

<span data-ttu-id="bf1c5-139">Ergebnisse:</span><span class="sxs-lookup"><span data-stu-id="bf1c5-139">Results:</span></span>

- <span data-ttu-id="bf1c5-140">Die Zugriffsgruppe „ProjectX-Members“ enthält die Benutzerkonten „Lead Designer“ und „Lead Researcher“.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-140">The ProjectX-Members access group contains the Lead Designer and Lead Researcher user accounts</span></span>

- <span data-ttu-id="bf1c5-141">Die Zugriffsgruppe „ProjectX-Admins“ enthält das globale Administratorkonto für das Testabonnement.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-141">The ProjectX-Admins access group contains the global administrator account for your trial subscription</span></span>

- <span data-ttu-id="bf1c5-142">Die Zugriffsgruppe „ProjectX-Viewers“ enthält das Benutzerkonto „Development VP“.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-142">The ProjectX-Viewers access group contains the Development VP user account</span></span>

<span data-ttu-id="bf1c5-143">Abbildung 1 zeigt die Zugriffsgruppen und ihre Mitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-143">Figure 1 shows the access groups and their membership.</span></span>

<span data-ttu-id="bf1c5-144">**Abbildung 1**</span><span class="sxs-lookup"><span data-stu-id="bf1c5-144">**Figure 1**</span></span>

![Die Office 365-Gruppen und deren Mitgliedschaft für eine isolierte SharePoint Online-Gruppenwebsite](../../media/5b7373b9-2a80-4880-afe5-63ffb17237e6.png)

## <a name="phase-3-create-a-new-projectx-sharepoint-online-team-site-and-isolate-it"></a><span data-ttu-id="bf1c5-146">Phase 3: Erstellen einer neuen SharePoint Online-Teamwebsite für ProjectX und Isolieren der Website</span><span class="sxs-lookup"><span data-stu-id="bf1c5-146">Phase 3: Create a new ProjectX SharePoint Online team site and isolate it</span></span>

<span data-ttu-id="bf1c5-147">Führen Sie folgende Schritte aus, um eine SharePoint Online-Teamwebsite für ProjectX zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="bf1c5-147">To create a SharePoint Online team site for ProjectX, do the following:</span></span>

1. <span data-ttu-id="bf1c5-148">Melden Sie sich über einen Browser auf dem lokalen Computer (kompakte Konfiguration) oder über CLIENT1 (simulierte Unternehmensumgebung) beim Office 365-Portal [https://admin.microsoft.com](https://admin.microsoft.com) unter Verwendung des globalen Administratorkontos an.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-148">Using a browser on either your local computer (lightweight configuration) or on CLIENT1 (simulated enterprise configuration), sign in to the Office 365 portal ([https://admin.microsoft.com](https://admin.microsoft.com)) using your global administrator account.</span></span>

2. <span data-ttu-id="bf1c5-149">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-149">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="bf1c5-150">Klicken Sie auf der neuen SharePoint-Registerkarte in Ihrem Browser auf **+ Website erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-150">On the new SharePoint tab in your browser, click **+ Create site**.</span></span>

4. <span data-ttu-id="bf1c5-p105">Geben Sie unter **Name der Teamwebsite** den Namen **ProjectX** ein. Wählen Sie in den **Datenschutzeinstellungen** die Option **Privat - nur Mitglieder können auf diese Website zugreifen** aus.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-p105">In **Team site name**, type **ProjectX**. In **Privacy settings**, select **Private - only members can access this site**.</span></span>

5. <span data-ttu-id="bf1c5-153">Geben Sie unter **Beschreibung der Teamwebsite** den Text **SharePoint-Website für ProjectX** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-153">In **Team site description**, type **SharePoint site for ProjectX**, and then click **Next**.</span></span>

6. <span data-ttu-id="bf1c5-154">Klicken Sie im Bereich **Wer soll hinzugefügt werden**? auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-154">On the **Who do you want to add**? pane, click **Finish**.</span></span>

7. <span data-ttu-id="bf1c5-155">Klicken Sie auf der neuen Registerkarte **ProjectX-Home** in Ihrem Browser auf der Symbolleiste auf das Symbol „Einstellungen", und klicken Sie dann auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-155">On the new **ProjectX-Home** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

8. <span data-ttu-id="bf1c5-156">Klicken Sie im Bereich **Websiteberechtigungen** auf **Erweiterte Berechtigungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-156">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>

9. <span data-ttu-id="bf1c5-157">Klicken Sie auf der neuen Registerkarte **Berechtigungen: ProjectX** in Ihrem Browser auf **Einstellungen für Zugriffsrechteanforderungen**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-157">In the new **Permissions: Project X** tab in your browser, click **Access Request Settings**.</span></span>

10. <span data-ttu-id="bf1c5-158">Deaktivieren Sie im Dialogfeld **Einstellungen für Zugriffsrechteanforderungen** die Optionen **Mitgliedern das Freigeben der Website sowie einzelner Dateien und Ordner erlauben** und **Zugriffsanforderungen zulassen** (sodass alle drei Kontrollkästchen deaktiviert sind), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-158">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

11. <span data-ttu-id="bf1c5-159">Klicken Sie in der Liste auf **ProjectX-Members**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-159">Click **ProjectX Members** in the list.</span></span>

12. <span data-ttu-id="bf1c5-160">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-160">On the **People and Groups** page, click **New**.</span></span>

13. <span data-ttu-id="bf1c5-161">Geben Sie im Dialogfeld **Freigeben** **ProjectX-Members** ein, wählen Sie die Option aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-161">In the **Share** dialog box, type **ProjectX-Members**, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="bf1c5-162">Klicken Sie auf die Schaltfläche „Zurück“ in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-162">Click the back button on your browser.</span></span>

15. <span data-ttu-id="bf1c5-163">Klicken Sie in der Liste auf **ProjectX-Owners**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-163">Click **ProjectX Owners** in the list.</span></span>

16. <span data-ttu-id="bf1c5-164">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-164">On the **People and Groups** page, click **New**.</span></span>

17. <span data-ttu-id="bf1c5-165">Geben Sie im Dialogfeld **Freigeben** **ProjectX-Admins** ein, wählen Sie die Option aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-165">In the **Share** dialog box, type **ProjectX-Admins**, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="bf1c5-166">Klicken Sie auf die Schaltfläche „Zurück“ in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-166">Click the back button on your browser.</span></span>

19. <span data-ttu-id="bf1c5-167">Klicken Sie in der Liste auf **ProjectX-Visitors**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-167">Click **ProjectX Visitors** in the list.</span></span>

20. <span data-ttu-id="bf1c5-168">Klicken Sie auf der Seite **Benutzer und Gruppen** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-168">On the **People and Groups** page, click **New**.</span></span>

21. <span data-ttu-id="bf1c5-169">Geben Sie im Dialogfeld **Freigeben** **ProjectX-Viewers** ein, wählen Sie die Option aus, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-169">In the **Share** dialog box, type **ProjectX-Viewers**, select it, and then click **Share**.</span></span>

22. <span data-ttu-id="bf1c5-170">Schließen Sie die Registerkarte **Benutzer und Gruppen** in Ihrem Browser, klicken Sie auf die Registerkarte **ProjectX-Home** in Ihrem Browser, und schließen Sie dann den Bereich **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-170">Close the **People and Groups** tab in your browser, click the **ProjectX-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>

<span data-ttu-id="bf1c5-171">Nachfolgend finden Sie die Ergebnisse der Konfiguration von Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="bf1c5-171">Here are the results of configuring permissions:</span></span>

- <span data-ttu-id="bf1c5-172">Die SharePoint-Gruppe „ProjectX Members“ enthält nur die Zugriffsgruppe „ProjectX-Members“ (die nur die Benutzerkonten „Lead Designer“ und „Lead Researcher“ enthält) und die Gruppe „ProjectX“ (die nur das Benutzerkonto des globalen Administrators enthält).</span><span class="sxs-lookup"><span data-stu-id="bf1c5-172">The ProjectX Members SharePoint group contains only the ProjectX-Members access group (which contains only the Lead Designer and Lead Researcher user accounts) and the ProjectX group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="bf1c5-173">Die SharePoint-Gruppe „ProjectX Owners“ enthält nur die Zugriffsgruppe „ProjectX-Admins“ (die nur das Benutzerkonto des globalen Administrators enthält).</span><span class="sxs-lookup"><span data-stu-id="bf1c5-173">The ProjectX Owners SharePoint group contains only the ProjectX-Admins access group (which contains only the global administrator user account).</span></span>

- <span data-ttu-id="bf1c5-174">Die SharePoint-Gruppe „ProjectX Visitors“ enthält nur die Zugriffsgruppe „ProjectX-Viewers“ (die nur das Benutzerkonto „Development VP“ enthält).</span><span class="sxs-lookup"><span data-stu-id="bf1c5-174">The ProjectX Visitors SharePoint group contains only the ProjectX-Viewers access group (which contains only the Development VP user account).</span></span>

- <span data-ttu-id="bf1c5-175">Mitglieder können keine Berechtigungen auf Websiteebene ändern (dies kann nur von Mitgliedern der Gruppe „ProjectX-Admins“ ausgeführt werden).</span><span class="sxs-lookup"><span data-stu-id="bf1c5-175">Members cannot modify site-level permissions (this can only be done by members of the ProjectX-Admins group).</span></span>

- <span data-ttu-id="bf1c5-176">Andere Benutzerkonten können nicht auf die Website oder ihre Ressourcen zugreifen oder Zugriff auf die Website anfordern.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-176">Other user accounts cannot access the site or its resources or request access to the site.</span></span>

<span data-ttu-id="bf1c5-177">In Abbildung 2 sind die SharePoint-Gruppen und ihre Mitgliedschaft dargestellt.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-177">Figure 2 shows the SharePoint groups and their membership.</span></span>

<span data-ttu-id="bf1c5-178">**Abbildung 2**</span><span class="sxs-lookup"><span data-stu-id="bf1c5-178">**Figure 2**</span></span>

![Die SharePoint Online-Gruppen und deren Mitgliedschaft für eine isolierte SharePoint Online-Gruppenwebsite](../../media/595abff4-64f9-49de-a37a-c70c6856936b.png)

<span data-ttu-id="bf1c5-180">Nachfolgend wird der Zugriff unter Verwendung des Lead Designer-Benutzerkontos veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="bf1c5-180">Now let's demonstrate access using the Lead Designer user account:</span></span>

1. <span data-ttu-id="bf1c5-181">Klicken Sie auf die Registerkarte **ProjectX-Home** in Ihrem Browser, und klicken Sie dann auf die Registerkarte **Microsoft Office Home** im Browser.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-181">Close the **ProjectX-Home** tab in your browser, and then click the **Microsoft Office Home** tab in your browser.</span></span>

2. <span data-ttu-id="bf1c5-182">Klicken Sie auf den Namen des globalen Administrators, und klicken Sie dann auf **Abmelden**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-182">Click the name of your global administrator, and then click **Sign out**.</span></span>

3. <span data-ttu-id="bf1c5-183">Melden Sie sich beim Office 365-Portal ([https://admin.microsoft.com](https://admin.microsoft.com)) mit dem Kontonamen und Kennwort des Lead Designers an.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-183">Sign in to the Office 365 portal ([https://admin.microsoft.com](https://admin.microsoft.com)) using the Lead Designer account name and its password.</span></span>

4. <span data-ttu-id="bf1c5-184">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-184">In the list of tiles, click **SharePoint**.</span></span>

5. <span data-ttu-id="bf1c5-p106">Geben Sie auf der neuen Registerkarte **SharePoint** in Ihrem Browser **ProjectX** in das Suchfeld ein, aktivieren Sie die Suche, und klicken Sie dann auf die Teamwebsite **ProjectX**. Für die ProjectX-Teamwebsite sollte nun eine neue Registerkarte im Browser angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-p106">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site. You should see a new tab in your browser for the ProjectX team site.</span></span>

6. <span data-ttu-id="bf1c5-p107">Klicken Sie auf das Symbol „Einstellungen". Beachten Sie, dass keine Option für **Websiteberechtigungen** vorhanden ist. Dies ist richtig, da nur die Mitglieder der Gruppe „ProjectX-Admins" Berechtigungen für die Website ändern können.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-p107">Click the settings icon. Notice that there is no option for **Site Permissions**. This is correct because only the members of the ProjectX-Admins group can modify permissions on the site</span></span>

7. <span data-ttu-id="bf1c5-190">Öffnen Sie Editor oder einen anderen Text-Editor Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-190">Open Notepad or a text editor of your choice.</span></span>

8. <span data-ttu-id="bf1c5-191">Kopieren Sie die URL der ProjectX-Teamwebsite, und fügen Sie sie in einer neuen Zeile in Editor oder in Ihrem Text-Editor ein.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-191">Copy the URL of the ProjectX team site and paste it on a new line in Notepad or your text editor.</span></span>

9. <span data-ttu-id="bf1c5-192">Klicken Sie auf der neuen Registerkarte **ProjectX-Home** im Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-192">On the new **ProjectX-Home** tab in your browser, click **Documents**.</span></span>

10. <span data-ttu-id="bf1c5-193">Kopieren Sie die URL des ProjectX-Dokumentordners, und fügen Sie sie in einer neuen Zeile in Editor oder in Ihrem Text-Editor ein.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-193">Copy the URL of the ProjectX documents folder and paste it on a new line in Notepad or your text editor.</span></span>

11. <span data-ttu-id="bf1c5-194">Klicken Sie auf der neuen Registerkarte **ProjectX-Dokumente** im Browser auf **Neu > Word-Dokument**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-194">On the new **ProjectX-Documents** tab in your browser, click **New > Word document**.</span></span>

12. <span data-ttu-id="bf1c5-195">Geben Sie Text auf der Seite ein, warten Sie, bis der Status **gespeichert**angezeigt wird, klicken Sie auf die Schaltfläche zurück in Ihrem Browser, und aktualisieren Sie dann die Seite.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-195">Type some text on the page, wait for the status to indicate **Saved**, click the back button on your browser, and then refresh the page.</span></span> <span data-ttu-id="bf1c5-196">Im Ordner **Dokumente** sollte nun ein neues Dokument **Document.docx** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-196">You should see a new **Document.docx** in the **Documents** folder.</span></span>

13. <span data-ttu-id="bf1c5-197">Klicken Sie auf die Auslassungspunkte für das Dokument **Document.docx**, und klicken Sie dann auf **Link abrufen**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-197">Click the ellipsis for the **Document.docx** document, and then click **Get a link**.</span></span>

14. <span data-ttu-id="bf1c5-198">Kopieren Sie die URL in das Dialogfeld **„Document.docx" freigeben**, und fügen Sie sie in einer neuen Zeile in Editor oder in Ihrem Text-Editor ein, und schließen Sie dann das Dialogfeld **„Document.docx"**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-198">Copy the URL in the **Share 'Document.docx'** dialog box and paste it on a new line in Notepad or your text editor, and then close the **Share 'Document.docx'** dialog box.</span></span>

15. <span data-ttu-id="bf1c5-199">Schließen Sie die Registerkarten **ProjectX-Dokumente** und **SharePoint** in Ihrem Browser, und klicken Sie dann auf die Registerkarte **Microsoft Office Home** im Browser.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-199">Close the **ProjectX-Documents** and **SharePoint** tabs in your browser, and then click the **Microsoft Office Home** tab.</span></span>

16. <span data-ttu-id="bf1c5-200">Klicken Sie auf den Namen **Lead Designer**, und klicken Sie dann auf **Abmelden**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-200">Click the **Lead Designer** name, and then click **Sign out**.</span></span>

<span data-ttu-id="bf1c5-201">Nachfolgend wird der Zugriff unter Verwendung des Development VP-Benutzerkontos veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="bf1c5-201">Now let's demonstrate access using the Development VP user account:</span></span>

1. <span data-ttu-id="bf1c5-202">Melden Sie sich beim Office 365-Portal ([https://admin.microsoft.com](https://admin.microsoft.com)) mit dem Kontonamen und Kennwort des Development VP an.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-202">Sign in to the Office 365 portal ([https://admin.microsoft.com](https://admin.microsoft.com)) using the Development VP account name and its password.</span></span>

2. <span data-ttu-id="bf1c5-203">Klicken Sie in der Liste der Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-203">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="bf1c5-p109">Geben Sie auf der neuen Registerkarte **SharePoint** in Ihrem Browser **ProjectX** in das Suchfeld ein, aktivieren Sie die Suche, und klicken Sie dann auf die Teamwebsite **ProjectX**. Für die ProjectX-Teamwebsite sollte nun eine neue Registerkarte im Browser angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-p109">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box, activate the search, and then click the **ProjectX** team site. You should see a new tab in your browser for the ProjectX team site.</span></span>

4. <span data-ttu-id="bf1c5-206">Klicken Sie auf **Dokumente**, und klicken Sie dann auf die Datei **Document.docx**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-206">Click **Documents**, and then click the **Document.docx** file.</span></span>

5. <span data-ttu-id="bf1c5-p110">Versuchen Sie, auf der Registerkarte **Document.docx** in Ihrem Browser den Text zu ändern. Es sollte eine Meldung angezeigt werden, die besagt, dass **dieses Dokument schreibgeschützt ist**. Dies wird erwartet, da das Development VP-Benutzerkonto nur über Anzeigeberechtigungen für die Website verfügt.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-p110">In the **Document.docx** tab in your browser, try to modify the text. You should see a message stating **This document is read-only.** This is expected because the Development VP user account only has view permissions for the site.</span></span>

6. <span data-ttu-id="bf1c5-210">Schließen Sie die Registerkarten **Document.docx**, **ProjectX-Dokumente** und **SharePoint** in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-210">Close the **Document.docx**, **ProjectX-Documents**, and **SharePoint** tabs in your browser.</span></span>

7. <span data-ttu-id="bf1c5-211">Klicken Sie auf der Registerkarte **Microsoft Office Home** auf den Namen **Development VP**, und klicken Sie dann auf **Abmelden**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-211">Click the **Microsoft Office Home** tab, click the **Development VP** name, and then click **Sign out**.</span></span>

<span data-ttu-id="bf1c5-212">Nachfolgend wird der Zugriff mit einem Benutzerkonto ohne Berechtigungen veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="bf1c5-212">Now let's demonstrate access with a user account that has no permissions:</span></span>

1. <span data-ttu-id="bf1c5-213">Melden Sie sich beim Office 365-Portal ([https://admin.microsoft.com](https://admin.microsoft.com)) mit dem Kontonamen und Kennwort von Benutzer 3 an.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-213">Sign in to the Office 365 portal ([https://admin.microsoft.com](https://admin.microsoft.com)) using the User 3 account name and its password.</span></span>

2. <span data-ttu-id="bf1c5-214">Klicken Sie in der Liste von Kacheln auf **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-214">In the list of tiles, click **SharePoint**.</span></span>

3. <span data-ttu-id="bf1c5-p111">Geben Sie auf der Registerkarte **SharePoint** in Ihrem Browser **ProjectX** im Suchfeld ein, aktivieren Sie dann die Suche. Es sollte die Meldung **Leider gibt es hierzu keine Suchergebnisse** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-p111">On the new **SharePoint** tab in your browser, type **ProjectX** in the search box and then activate the search. You should see the message **Nothing here matches your search.**</span></span>

4. <span data-ttu-id="bf1c5-p112">Kopieren Sie aus der geöffneten Instanz von Editor oder Ihres Text-Editors die URL für die ProjectX-Website in die Adressleiste Ihres Browsers, und drücken Sie die **EINGABETASTE**. Die Seite **Zugriff verweigert** sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-p112">From the open instance of Notepad or your text editor, copy the URL for the ProjectX site into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

5. <span data-ttu-id="bf1c5-p113">Kopieren Sie aus Editor oder aus Ihrem Text-Editor die URL für den ProjectX-Dokumenteordner in die Adressleiste Ihres Browsers, und drücken Sie die **EINGABETASTE**. Die Seite **Zugriff verweigert** sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-p113">From Notepad or your text editor, copy the URL for the ProjectX Documents folder into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

6. <span data-ttu-id="bf1c5-p114">Kopieren Sie aus Editor oder aus Ihrem Text-Editor die URL für die Datei „Documents.docx" in die Adressleiste Ihres Browsers, und drücken Sie die **EINGABETASTE**. Die Seite **Zugriff verweigert** sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-p114">From Notepad or your text editor, copy the URL for the Documents.docx file into the address bar of your browser and press **Enter**. You should see an **Access Denied** page.</span></span>

7. <span data-ttu-id="bf1c5-223">Schließen Sie die Registerkarte **SharePoint** in Ihrem Browser, klicken Sie auf die Registerkarte **Microsoft Office Home**, klicken Sie auf den Namen **Benutzer 3**, und klicken Sie dann auf **Abmelden**.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-223">Close the **SharePoint** tab in your browser, click the **Microsoft Office Home** tab, click the **User 3** name, and then click **Sign out**.</span></span>

<span data-ttu-id="bf1c5-224">Sie können nun weiter mit der isolierten SharePoint Online-Website experimentieren.</span><span class="sxs-lookup"><span data-stu-id="bf1c5-224">Your isolated SharePoint Online site is now ready for your additional experimentation.</span></span>

## <a name="next-step"></a><span data-ttu-id="bf1c5-225">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="bf1c5-225">Next Step</span></span>

<span data-ttu-id="bf1c5-226">Wenn Sie eine isolierte SharePoint Online-Teamwebsite in der Produktion bereitstellen möchten, lesen Sie die schrittweisen Überlegungen zum Entwurf unter [Entwerfen einer isolierten SharePoint Online-Teamwebsite](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="bf1c5-226">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bf1c5-227">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf1c5-227">See Also</span></span>

[<span data-ttu-id="bf1c5-228">Isolierte SharePoint Online-Teamwebsites</span><span class="sxs-lookup"><span data-stu-id="bf1c5-228">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="bf1c5-229">Testumgebungsanleitungen (TLGs) zur Cloudakzeptanz</span><span class="sxs-lookup"><span data-stu-id="bf1c5-229">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[<span data-ttu-id="bf1c5-230">Basiskonfiguration der Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="bf1c5-230">Base Configuration dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/base-configuration-dev-test-environment)

[<span data-ttu-id="bf1c5-231">Office 365-Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="bf1c5-231">Office 365 dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)

[<span data-ttu-id="bf1c5-232">Cloudakzeptanz und Hybridlösungen</span><span class="sxs-lookup"><span data-stu-id="bf1c5-232">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)




