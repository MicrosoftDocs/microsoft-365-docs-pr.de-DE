---
title: Sichere Teams für Dateien in einer Entwicklungs-/Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: 'Zusammenfassung: Erstellen von vertraulichen und streng vertraulichen Teams in Microsoft Teams für Dateien in einer Entwicklungs-/Testumgebung.'
ms.openlocfilehash: f22b3b1fbe07af6866206034ad6c9a90ced8a268
ms.sourcegitcommit: 6dfa646b9de30336dedfd0cac7320c57ad74ae11
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "37929263"
---
# <a name="secure-teams-for-files-in-a-devtest-environment"></a><span data-ttu-id="e82a2-103">Sichere Teams für Dateien in einer Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="e82a2-103">Secure Teams for files in a dev/test environment</span></span>

<span data-ttu-id="e82a2-104">In diesem Artikel finden Sie schrittweise Anleitungen zum Erstellen einer Entwicklungs-/Testumgebung, die die vertraulichen und streng vertraulichen Teams für die Lösung [Sichern von Dateien in Microsoft Teams](secure-files-in-teams.md) umfasst.</span><span class="sxs-lookup"><span data-stu-id="e82a2-104">This article provides step-by-step instructions to create a dev/test environment that includes the sensitive and highly confidential teams for the [Secure files in Microsoft Teams](secure-files-in-teams.md) solution.</span></span>
  
![Vertrauliche und streng vertrauliche Teams in Microsoft Teams für Dateien.](../media/sensitive-highly-confidential-teams-dev-test.png)
  
<span data-ttu-id="e82a2-106">Verwenden Sie diese Entwicklungs-/Testumgebung, um Einstellungen für Ihre spezifischen Anforderungen auszuprobieren und zu optimieren, bevor Sie diese Arten von Teams in der Produktion bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e82a2-106">Use this dev/test environment to experiment with the information protection behaviors and fine-tune settings for your specific needs before deploying SharePoint Online team sites in production.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e82a2-107">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="e82a2-107">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="e82a2-108">Wenn Sie vertrauliche und streng vertrauliche Teams auf einfache Weise mit Minimalanforderungen testen möchten, befolgen Sie die Anweisungen unter [Einfache Basiskonfiguration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="e82a2-108">If you just want to test sensitive and highly confidential teams in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](https://docs.microsoft.com/microsoft-365/enterprise/lightweight-base-configuration-microsoft-365-enterprise).</span></span>

<span data-ttu-id="e82a2-109">Wenn Sie vertrauliche und streng vertrauliche Teams in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span><span class="sxs-lookup"><span data-stu-id="e82a2-109">If you want to test sensitive and highly confidential teams in a simulated enterprise, follow the instructions in [Password hash synchronization](https://docs.microsoft.com/microsoft-365/enterprise/password-hash-sync-m365-ent-test-environment).</span></span>

>[!Note]
><span data-ttu-id="e82a2-110">Für das Testen von vertraulichen und streng vertraulichen Teams ist keine simulierte Unternehmenstestumgebung erforderlich, die ein simuliertes Intranet, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für eine Active Directory Domain Services-Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="e82a2-110">Testing sensitive and highly confidential teams does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="e82a2-111">Dies wird hier als Option bereitgestellt, damit Sie vertrauliche und streng vertrauliche Teams testen und damit in einer Umgebung, die eine typische Organisation darstellt, experimentieren können.</span><span class="sxs-lookup"><span data-stu-id="e82a2-111">It is provided here as an option so that you can test sensitive file protection and experiment with it in an environment that represents a typical organization.</span></span>
>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a><span data-ttu-id="e82a2-112">Phase 2: Erstellen und Konfigurieren der Azure Active Directory(AD)-Gruppen und -Benutzer</span><span class="sxs-lookup"><span data-stu-id="e82a2-112">Phase 2: Create and configure your Azure Active Directory (AD) groups and users</span></span>

<span data-ttu-id="e82a2-113">In dieser Phase erstellen und konfigurieren Sie die Azure AD-Gruppen und -Benutzer für eine fiktive Organisation.</span><span class="sxs-lookup"><span data-stu-id="e82a2-113">In this phase, you create and configure the Azure AD groups and users for your fictional organization.</span></span>
  
<span data-ttu-id="e82a2-114">Erstellen Sie zuerst zwei Gruppen für eine typische Organisation mit dem Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="e82a2-114">First, create a set of groups for a typical organization with the Azure portal.</span></span>
  
1. <span data-ttu-id="e82a2-115">Erstellen Sie eine separate Registerkarte in Ihrem Browser, und wechseln Sie dann zum Azure-Portal unter [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="e82a2-115">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span> <span data-ttu-id="e82a2-116">Falls erforderlich, melden Sie sich mit den Anmeldeinformationen des globalen Administratorkontos für Ihr Microsoft 365 E5-Testabonnement oder Ihr kostenpflichtiges Abonnement an.</span><span class="sxs-lookup"><span data-stu-id="e82a2-116">If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>
    
2. <span data-ttu-id="e82a2-117">Klicken Sie im Azure-Portal auf **Azure Active Directory > Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-117">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="e82a2-118">Klicken Sie auf dem Blatt **Gruppen - Alle Gruppen** auf **+ Neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-118">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="e82a2-119">Auf dem Blatt **Gruppe**:</span><span class="sxs-lookup"><span data-stu-id="e82a2-119">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="e82a2-120">Wählen Sie unter **Gruppentyp** die Option **Sicherheit** aus.</span><span class="sxs-lookup"><span data-stu-id="e82a2-120">Select **Office 365** in **Group type**.</span></span>
    
  - <span data-ttu-id="e82a2-121">Geben **C-Suite** unter **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="e82a2-121">Type **C-Suite** in **Name**.</span></span>
    
  - <span data-ttu-id="e82a2-122">Wählen Sie **Zugewiesen** unter **Mitgliedschaftstyp** aus.</span><span class="sxs-lookup"><span data-stu-id="e82a2-122">Select **Assigned** in **Membership type**.</span></span>
      
5. <span data-ttu-id="e82a2-123">Klicken Sie auf **Erstellen**, und schließen Sie dann das Blatt **Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-123">Click **Create**, and then close the **Group** blade.</span></span>
    
6.  <span data-ttu-id="e82a2-124">Wiederholen Sie die Schritte 3-5 für eine neue folgende Gruppe namens **Marketingmitarbeiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-124">Repeat steps 3-5 for a new following group named **Marketing staff**.</span></span>
    
<span data-ttu-id="e82a2-125">Im nächsten Schritt wird die automatische Lizenzierung konfiguriert, sodass Mitgliedern von Gruppen automatisch Lizenzen für Ihre Office 365- und EMS-Abonnements zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e82a2-125">Next, you configure automatic licensing so that members of your groups are automatically assigned licenses for your Office 365 and EMS subscriptions.</span></span>
  
1. <span data-ttu-id="e82a2-126">Klicken Sie im Azure-Portal auf **Azure Active Directory > Lizenzen > Alle Produkte**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-126">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>
    
2. <span data-ttu-id="e82a2-127">Wählen Sie in der Liste **Microsoft 365 Enterprise E5** aus, und klicken Sie dann auf **Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-127">In the list, select **Enterprise Mobility + Security E5 and Office 365 Enterprise E5**, and then click **Assign**.</span></span>
    
3. <span data-ttu-id="e82a2-128">Klicken Sie auf dem Blatt **Lizenz zuweisen** auf **Benutzer und Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-128">In the **Assign license** blade, click **Users and groups**.</span></span>
    
4. <span data-ttu-id="e82a2-129">Wählen Sie in der Liste der Gruppen Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="e82a2-129">In the list of groups, select the following:</span></span>
    
  - <span data-ttu-id="e82a2-130">C-Suite</span><span class="sxs-lookup"><span data-stu-id="e82a2-130">C-Suite</span></span>
    
  - <span data-ttu-id="e82a2-131">Marketingmitarbeiter</span><span class="sxs-lookup"><span data-stu-id="e82a2-131">Marketing staff</span></span>
    
5. <span data-ttu-id="e82a2-132">Klicken Sie auf **Auswählen** und dann auf **Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-132">Click **Select**, and then click **Assign**.</span></span>
    
6. <span data-ttu-id="e82a2-133">Schließen Sie die Registerkarte für das Azure Portal in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="e82a2-133">Close the Azure portal tab in your browser.</span></span>
    
<span data-ttu-id="e82a2-134">Danach müssen Sie [eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Module herstellen](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="e82a2-134">Next, you [Connect with the Azure Active Directory PowerShell for Graph module ](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="e82a2-135">Geben Sie den Namen Ihrer Organisation, Ihren Standort und ein gemeinsames Kennwort ein, und führen Sie dann die folgenden Befehle über die PowerShell-Eingabeaufforderung oder in der ISE-Umgebung (Integrated Script Environment) aus, um Benutzerkonten zu erstellen und sie zu den Gruppen hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="e82a2-135">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create user accounts and add them to their groups:</span></span>
  
```
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> <span data-ttu-id="e82a2-136">Für die Automatisierung und Vereinfachung der Konfiguration einer Dev/Test-Umgebung wird hier ein gemeinsames Kennwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="e82a2-136">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="e82a2-137">Natürlich ist davon bei Produktionsabonnements dringend abzuraten.</span><span class="sxs-lookup"><span data-stu-id="e82a2-137">Obviously, this is highly discouraged for production subscriptions.</span></span> 
  
<span data-ttu-id="e82a2-138">Gehen Sie folgendermaßen vor, um sicherzustellen, dass die gruppenbasierte Lizenzierung ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="e82a2-138">Use these steps to verify that group-based licensing is working correctly.</span></span>
  
1. <span data-ttu-id="e82a2-139">Klicken Sie auf der Registerkarte **Microsoft Office Home** in Ihrem Browser auf die Kachel **Admin**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-139">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>
    
2. <span data-ttu-id="e82a2-140">Klicken Sie auf der neuen Registerkarte **Microsoft 365 Admin Center** des Browsers auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-140">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>
    
3. <span data-ttu-id="e82a2-141">Klicken Sie in der Liste der Benutzer auf **CEO**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-141">In the list of users, click **CEO**.</span></span>
    
4. <span data-ttu-id="e82a2-142">Stellen Sie im Bereich, der die Eigenschaften des Benutzerkontos **CEO** anzeigt, sicher, dass ihm die Lizenz **Microsoft 365 Enterprise E5** zugewiesen wurde (in **Produktlizenzen**).</span><span class="sxs-lookup"><span data-stu-id="e82a2-142">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Enterprise Mobility + Security E5 and Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>
    
## <a name="phase-3-create-office-365-retention-labels"></a><span data-ttu-id="e82a2-143">Phase 3: Erstellen von Office 365-Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="e82a2-143">Phase 3: Create Office 365 retention labels</span></span>

<span data-ttu-id="e82a2-144">In dieser Phase erstellen Sie die Aufbewahrungsbezeichnungen für die verschiedenen Sicherheitsstufen für Dokumentordner für die zugrunde liegende SharePoint-Website.</span><span class="sxs-lookup"><span data-stu-id="e82a2-144">In this phase, you create the retention labels for the different levels of security for SharePoint Online team site documents folders.</span></span>

1. <span data-ttu-id="e82a2-145">Melden Sie sich beim [Microsoft 365 Compliance-Portal](https://compliance.microsoft.com) mit Ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="e82a2-145">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="e82a2-146">Klicken Sie auf der Registerkarte \*\*Start – Microsoft 365 Compliance \*\* im Browser auf **Klassifizierungen > Bezeichnungen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-146">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="e82a2-147">Klicken Sie auf **Aufbewahrungsbezeichnung > Erstellen einer Bezeichnung**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-147">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="e82a2-148">Geben Sie im Bereich **Name für Bezeichnung** unter **Name für Bezeichnung** **Vertraulich** ein, und klicken Sie dann auf **Weiter**</span><span class="sxs-lookup"><span data-stu-id="e82a2-148">On the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="e82a2-149">Klicken Sie im Bereich **Dateiplanbeschreibungen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-149">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="e82a2-150">Legen Sie im Bereich **Bezeichnungseigenschaften**, falls erforderlich, **Aufbewahrung** auf **Ein** fest, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-150">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="e82a2-151">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Beschriftung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-151">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="e82a2-152">Wiederholen Sie die Schritte 3-7 für eine zusätzliche Aufbewahrungsbezeichnung namens **Streng vertraulich**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-152">Repeat steps 3-7 for an additional retention label named **Highly Confidential**.</span></span>
    
9. <span data-ttu-id="e82a2-153">Klicken Sie im Bereich **Startseite > Bezeichnungen** auf **Bezeichnungen veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-153">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="e82a2-154">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Zu veröffentlichende Bezeichnungen wählen**</span><span class="sxs-lookup"><span data-stu-id="e82a2-154">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="e82a2-155">Klicken Sie im Bereich **Choose labels** (Bezeichnungen auswählen) auf **Hinzufügen**, wählen Sie alle vier Bezeichnungen aus.</span><span class="sxs-lookup"><span data-stu-id="e82a2-155">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="e82a2-156">Klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-156">Click **Done**.</span></span>
    
13. <span data-ttu-id="e82a2-157">Klicken Sie im Bereich **Zu veröffentlichende Bezeichnungen wählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-157">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="e82a2-158">Klicken Sie im Bereich **Speicherorte auswählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-158">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="e82a2-159">Geben Sie im Bereich **Richtlinie benennen** **Beispielorganisation** unter **Name** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-159">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="e82a2-160">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Bezeichnungen veröffentlichen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-160">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-4-create-your-teams"></a><span data-ttu-id="e82a2-161">Phase 4: Erstellen Ihrer Teams</span><span class="sxs-lookup"><span data-stu-id="e82a2-161">Phase 4: Create your teams</span></span>

<span data-ttu-id="e82a2-162">In dieser Phase erstellen und konfigurieren Sie vertrauliche und streng vertrauliche Teams für Ihre Beispielorganisation.</span><span class="sxs-lookup"><span data-stu-id="e82a2-162">In this phase, you create and configure sensitive and highly confidential teams for your example organization.</span></span>

### <a name="sensitive-team-for-marketing-campaigns"></a><span data-ttu-id="e82a2-163">Vertrauliches Team für Marketingkampagnen</span><span class="sxs-lookup"><span data-stu-id="e82a2-163">Sensitive team for marketing campaigns</span></span>

<span data-ttu-id="e82a2-164">Gehen Sie folgendermaßen vor, um ein Team auf der Ebene „Vertraulich“ für Mitglieder der Marketinggruppe zu erstellen, damit Sie an laufenden Marketingkampagnen zusammenarbeiten können:</span><span class="sxs-lookup"><span data-stu-id="e82a2-164">To create a sensitive-level team for members of the marketing group to collaborate on ongoing marketing campaigns:</span></span>

1. <span data-ttu-id="e82a2-165">[Erstellen Sie ein neues privates Team](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) mit dem Namen **Marketingkampagnen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-165">[Create a new private team](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) with the name **Marketing Campaigns**.</span></span>
2. <span data-ttu-id="e82a2-166">Öffnen Sie das Team **Marketingkampagnen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-166">Open the **Marketing Campaigns** team.</span></span>
3.  <span data-ttu-id="e82a2-167">Klicken Sie auf der Symbolleiste des Teams auf **Dateien**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-167">In the tool bar for the team, click **Files**.</span></span>
4.  <span data-ttu-id="e82a2-168">Klicken Sie auf die drei Punkte "(…)" und dann auf **In SharePoint öffnen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-168">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
5.  <span data-ttu-id="e82a2-169">Klicken Sie in der Symbolleiste der zugrunde liegenden SharePoint-Website auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-169">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
6.  <span data-ttu-id="e82a2-170">Klicken Sie im Bereich **Websiteberechtigungen** unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-170">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
7.  <span data-ttu-id="e82a2-171">Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-171">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>

<span data-ttu-id="e82a2-172">Konfigurieren Sie anschließend den Ordner „Dokumente“ der zugrunde liegenden SharePoint-Website „Marketingkampagnen“ für die Bezeichnung „Vertraulich“.</span><span class="sxs-lookup"><span data-stu-id="e82a2-172">Next, configure the documents folder of the Marketing campaigns team site for the Sensitive label.</span></span>

1.  <span data-ttu-id="e82a2-173">Klicken Sie auf der Registerkarte **Marketingkampagnen – Startseite** in Ihrem Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-173">In the **Marketing campaigns-Home** tab of your browser, click **Documents**.</span></span>
2.  <span data-ttu-id="e82a2-174">Klicken Sie auf das Symbol „Einstellungen“, und klicken Sie dann auf **Bibliothekseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-174">Click the settings icon, and then click **Library settings**.</span></span>
3.  <span data-ttu-id="e82a2-175">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-175">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
4.  <span data-ttu-id="e82a2-176">Wählen Sie unter **Einstellungen -Bezeichnung anwenden** die Option **Vertraulich**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-176">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span> 

<span data-ttu-id="e82a2-177">Konfigurieren Sie als Nächstes eine Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP), die Benutzer benachrichtigt, wenn sie ein Dokument auf einer der zugrunde liegenden SharePoint-Website mit der Bezeichnung „Vertraulich“ freigeben, die die Marketingkampagnenwebsite enthält (außerhalb der Organisation).</span><span class="sxs-lookup"><span data-stu-id="e82a2-177">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label, which includes the Marketing campaigns site, outside the organization.</span></span>

1. <span data-ttu-id="e82a2-178">Melden Sie sich beim [Microsoft 365 Compliance-Portal](https://compliance.microsoft.com/) mit Ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="e82a2-178">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin account.</span></span>
    
2. <span data-ttu-id="e82a2-179">Klicken Sie auf der Registerkarte **Microsoft 365 Compliance** in Ihrem Browser auf **Richtlinien > Verhinderung von Datenverlust**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-179">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="e82a2-180">Klicken Sie im Bereich **Verhinderung von Datenverlust** auf **Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-180">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="e82a2-181">Klicken Sie im Bereich **Mit einer Vorlage beginnen oder eine benutzerdefinierte Richtlinie erstellen** auf **Benutzerdefiniert**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-181">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="e82a2-182">Geben Sie im Bereich **Ihre Richtlinie benennen** den Namen **Bezeichnung „Vertraulich" – SharePoint-Websites** bei **Name** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-182">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="e82a2-183">Klicken Sie im Bereich **Speicherorte auswählen** auf **Bestimmte Speicherorte auswählen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-183">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="e82a2-184">Deaktivieren Sie in der Liste der Speicherorte **Exchange-E-Mail**, **OneDrive-Konten** und **Teams-Chat- und Kanalnachrichten**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-184">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="e82a2-185">Klicken Sie im Bereich **Anpassen des zu schützenden Inhaltstyps** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-185">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="e82a2-186">In der **wählen Sie die Typen der Inhalte zum Schutz** Bereich, klicken Sie auf **hinzufügen** im Dropdown-Listenfeld, und klicken Sie dann auf **Aufbewahrungsbezeichnungen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-186">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="e82a2-187">Klicken Sie im Bereich **Aufbewahrungsbezeichnungen** auf **Hinzufügen**, wählen Sie die Bezeichnung **Vertraulich** aus, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-187">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="e82a2-188">Klicken Sie im Bereich **Typen des zu schützenden Inhalts auswählen** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-188">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="e82a2-189">Klicken Sie im Bereich **Anpassen des zu schützenden Inhaltstyps** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-189">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="e82a2-190">Klicken Sie im Bereich **Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?** auf **Richtlinientipptext anpassen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-190">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="e82a2-191">Klicken Sie im Bereich **Customize policy tips and email notifications** (Anpassen der Richtlinientipps und der E-Mail-Benachrichtigungen) auf **Customize the policy tip text** (Den Tipptext der Richtlinie als nächstes anpassen).</span><span class="sxs-lookup"><span data-stu-id="e82a2-191">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="e82a2-192">Geben Sie Folgendes in das Textfeld ein, oder fügen Sie es ein:</span><span class="sxs-lookup"><span data-stu-id="e82a2-192">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="e82a2-p104">Wenn Sie eine Datei für einen Benutzer außerhalb der Organisation freigeben möchten, laden Sie die Datei herunter, und öffnen Sie sie. Klicken Sie auf „Datei“ > „Dokument schützen“ > „Mit Kennwort verschlüsseln“, und geben Sie dann ein sicheres Kennwort ein. Senden Sie das Kennwort in einer separaten E-Mail oder auf andere Weise.</span><span class="sxs-lookup"><span data-stu-id="e82a2-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="e82a2-196">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-196">Click **OK**.</span></span>
    
17. <span data-ttu-id="e82a2-197">Klicken Sie im Bereich **Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-197">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="e82a2-198">Klicken Sie im Bereich **Möchten Sie die Richtlinie aktivieren oder zunächst testen?** auf **Ja, Richtlinie aktivieren**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-198">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="e82a2-199">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-199">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="e82a2-200">Hier ist die resultierende Konfiguration für das Marketingkampagnenteam.</span><span class="sxs-lookup"><span data-stu-id="e82a2-200">Here is the resulting configuration for the Marketing Campaigns team.</span></span>

![Konfiguration für das Marketingkampagnenteam.](../media/sensitive-team-config-dev-test.png)
  
### <a name="company-strategy-team-site"></a><span data-ttu-id="e82a2-202">Teamwebsite für Unternehmensstrategie</span><span class="sxs-lookup"><span data-stu-id="e82a2-202">Company strategy team site</span></span>

<span data-ttu-id="e82a2-203">Gehen Sie folgendermaßen vor, um ein Team auf der Ebene „Streng vertraulich“ für Mitglieder des Geschäftsleitungsteams zu erstellen, damit Sie an der Unternehmensstrategie zusammenarbeiten können:</span><span class="sxs-lookup"><span data-stu-id="e82a2-203">To create a highly confidential-level team for members of the senior leadership team to collaborate on company strategy:</span></span>

1. <span data-ttu-id="e82a2-204">[Erstellen Sie ein neues privates Team](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) mit dem Namen **Unternehmensstrategie**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-204">[Create a new private team](https://support.office.com//article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) with the name **Company Strategy**.</span></span>
2. <span data-ttu-id="e82a2-205">Öffnen Sie das Team **Unternehmensstrategie**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-205">Open the **Company Strategy** team.</span></span>
3.  <span data-ttu-id="e82a2-206">Klicken Sie auf der Symbolleiste des Teams auf **Dateien**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-206">In the tool bar for the team, click **Files**.</span></span>
4.  <span data-ttu-id="e82a2-207">Klicken Sie auf die drei Punkte "(…)" und dann auf **In SharePoint öffnen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-207">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
5.  <span data-ttu-id="e82a2-208">Klicken Sie in der Symbolleiste der zugrunde liegenden SharePoint-Website auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-208">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
6.  <span data-ttu-id="e82a2-209">Klicken Sie im Bereich **Websiteberechtigungen** unter **Freigabeeinstellungen** auf **Freigabeeinstellungen ändern**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-209">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
7.  <span data-ttu-id="e82a2-210">Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus.</span><span class="sxs-lookup"><span data-stu-id="e82a2-210">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
8.  <span data-ttu-id="e82a2-211">Deaktivieren Sie **Zugriffsanforderungen zulassen**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-211">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="e82a2-212">Konfigurieren Sie anschließend den Ordner „Dokumente“ der zugrunde liegenden SharePoint-Website „Unternehmensstrategie“ für die Bezeichnung „Streng vertraulich“.</span><span class="sxs-lookup"><span data-stu-id="e82a2-212">Next, configure the documents folder of the Company strategy team site for the Highly Confidential label.</span></span>

1.  <span data-ttu-id="e82a2-213">Klicken Sie auf der Registerkarte **Unternehmensstrategie – Startseite** in Ihrem Browser auf **Dokumente**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-213">In the **Company strategy-Home** tab of your browser, click **Documents**.</span></span>
2.  <span data-ttu-id="e82a2-214">Klicken Sie auf das Symbol „Einstellungen“, und klicken Sie dann auf **Bibliothekseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-214">Click the settings icon, and then click **Library settings**.</span></span>
3.  <span data-ttu-id="e82a2-215">Klicken Sie unter **Berechtigungen und Verwaltung** auf **Bezeichnung auf Elemente in dieser Bibliothek anwenden**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-215">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
4.  <span data-ttu-id="e82a2-216">Wählen Sie unter **Einstellungen -Bezeichnung anwenden** die Option **Streng vertraulich**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-216">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span> 

<span data-ttu-id="e82a2-217">Konfigurieren Sie als Nächstes eine DLP-Richtlinie, die Benutzer blockiert, wenn sie ein Dokument auf einer zugrunde liegenden SharePoint-Website mit der Bezeichnung „Streng vertraulich" freigeben, die die Unternehmensstrategiewebsite enthält (außerhalb der Organisation).</span><span class="sxs-lookup"><span data-stu-id="e82a2-217">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label, which includes the Company strategy site, outside the organization.</span></span>
  
1. <span data-ttu-id="e82a2-218">Melden Sie sich beim [Microsoft 365 Compliance-Portal](https://compliance.microsoft.com/) mit Ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="e82a2-218">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin.</span></span>
    
2. <span data-ttu-id="e82a2-219">Klicken Sie auf der Registerkarte **Microsoft 365 Compliance** in Ihrem Browser auf **Richtlinien > Verhinderung von Datenverlust**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-219">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="e82a2-220">Klicken Sie im Bereich **Verhinderung von Datenverlust** auf **Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-220">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="e82a2-221">Klicken Sie im Bereich **Mit einer Vorlage beginnen oder eine benutzerdefinierte Richtlinie erstellen** auf **Benutzerdefiniert**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-221">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="e82a2-222">Geben Sie im Bereich **Ihre Richtlinie benennen** den Namen **Bezeichnung „Streng vertraulich" – SharePoint-Websites** bei **Name** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-222">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="e82a2-223">Klicken Sie im Bereich **Speicherorte auswählen** auf **Bestimmte Speicherorte auswählen**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-223">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="e82a2-224">Deaktivieren Sie in der Liste der Speicherorte **Exchange-E-Mail**, **OneDrive-Konten** und **Teams-Chat- und Kanalnachrichten**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-224">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="e82a2-225">Klicken Sie im Bereich **Anpassen des zu schützenden Inhaltstyps** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-225">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="e82a2-226">In der **wählen Sie die Typen der Inhalte zum Schutz** Bereich, klicken Sie auf **hinzufügen** im Dropdown-Listenfeld, und klicken Sie dann auf **Aufbewahrungsbezeichnungen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-226">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="e82a2-227">Klicken Sie im Bereich **Aufbewahrungsbezeichnungen** auf **Hinzufügen**, wählen Sie die Bezeichnung **Streng vertraulich** aus, klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-227">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="e82a2-228">Klicken Sie im Bereich **Typen des zu schützenden Inhalts auswählen** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-228">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="e82a2-229">Klicken Sie im Bereich **Anpassen des zu schützenden Inhaltstyps** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-229">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="e82a2-230">Klicken Sie im Bereich **Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?** auf **Richtlinientipptext anpassen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-230">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="e82a2-231">Klicken Sie im Bereich **Customize policy tips and email notifications** (Anpassen der Richtlinientipps und der E-Mail-Benachrichtigungen) auf **Customize the policy tip text** (Den Tipptext der Richtlinie als nächstes anpassen).</span><span class="sxs-lookup"><span data-stu-id="e82a2-231">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="e82a2-232">Geben Sie Folgendes in das Textfeld ein, oder fügen Sie es ein:</span><span class="sxs-lookup"><span data-stu-id="e82a2-232">In the text box, type or paste in the following:</span></span>
    
  - <span data-ttu-id="e82a2-p105">Wenn Sie eine Datei für einen Benutzer außerhalb der Organisation freigeben möchten, laden Sie die Datei herunter, und öffnen Sie sie. Klicken Sie auf „Datei“ > „Dokument schützen“ > „Mit Kennwort verschlüsseln“, und geben Sie dann ein sicheres Kennwort ein. Senden Sie das Kennwort in einer separaten E-Mail oder auf andere Weise.</span><span class="sxs-lookup"><span data-stu-id="e82a2-p105">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="e82a2-236">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-236">Click **OK**.</span></span>
    
17. <span data-ttu-id="e82a2-237">Klicken Sie im Bereich **Möchten Sie die Richtlinie aktivieren oder zunächst testen?** auf **Ja, Richtlinie aktivieren**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-237">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

18. <span data-ttu-id="e82a2-238">Klicken Sie im Bereich **Möchten Sie die Richtlinie aktivieren oder zunächst testen?** auf **Ja, Richtlinie aktivieren**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-238">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="e82a2-239">Klicken Sie im Bereich **Einstellungen überprüfen** auf **Erstellen**, und klicken Sie dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="e82a2-239">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>

<span data-ttu-id="e82a2-240">Verwenden Sie [diese Anweisungen ](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) zum Konfigurieren einer Vertraulichkeitsbezeichnung mit den folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="e82a2-240">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="e82a2-241">Der Name der Bezeichnung lautet „Unternehmensstrategie“.</span><span class="sxs-lookup"><span data-stu-id="e82a2-241">The name of the label is Company Strategy</span></span>
- <span data-ttu-id="e82a2-242">Die Verschlüsselung ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e82a2-242">Encryption is enabled</span></span>
- <span data-ttu-id="e82a2-243">Die Gruppe „Unternehmensstrategie“ verfügt über Berechtigungen für die gemeinsame Dokumenterstellung.</span><span class="sxs-lookup"><span data-stu-id="e82a2-243">The site group has Co-Author permissions.</span></span>

<span data-ttu-id="e82a2-244">Veröffentlichen Sie nach dem Erstellen die neue Bezeichnung.</span><span class="sxs-lookup"><span data-stu-id="e82a2-244">After creating, publish the new label.</span></span> <span data-ttu-id="e82a2-245">Wenn Sie sich als Mitglied der Gruppe „Unternehmensstrategie“ anmelden, wird die neue Bezeichnung auf der Symbolleiste „Start“ in Word, Excel und PowerPoint unter der Option „Vertraulichkeit“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e82a2-245">If you sign in as a member of the Company Strategy group, you will see the new label in the Sensitivity option in the Home toolbar of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="e82a2-246">Wählen Sie unter der Option „Vertraulichkeit“ die Bezeichnung „Unternehmensstrategie“ aus, um einer Datei eine Bezeichnung zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="e82a2-246">Select the Company Strategy label from the Sensitivity option to assign the label to a file.</span></span>

<span data-ttu-id="e82a2-247">Hier ist die resultierende Konfiguration für das Unternehmensstrategieteam.</span><span class="sxs-lookup"><span data-stu-id="e82a2-247">Here is the resulting configuration for the Company Strategy team.</span></span>

![Konfiguration für das Team „Unternehmensstrategie“.](../media/highlyconfidential-team-config-dev-test.png) 

<span data-ttu-id="e82a2-249">Dateien im Abschnitt „Dokumente“ der zugrunde liegenden SharePoint-Website „Unternehmensstrategie“ wird die Aufbewahrungsbezeichnung „Streng vertraulich“ zugewiesen, und sie unterliegen der konfigurierten DLP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="e82a2-249">Files in the documents section of the underlying Company Strategy SharePoint site are assigned the Highly confidential retention label and are subject to the configured DLP policy.</span></span> <span data-ttu-id="e82a2-250">Für Dateien kann auch die Vertraulichkeitsbezeichnung „Unternehmensstrategie“ zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e82a2-250">Files can also have the Company Strategy sensitivity label assigned.</span></span>    
  
## <a name="next-step"></a><span data-ttu-id="e82a2-251">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="e82a2-251">Next step</span></span>

<span data-ttu-id="e82a2-252">Wenn Sie für die Produktionsbereitstellung finden Sie unter [Sichern von Dateien in Microsoft Teams](secure-files-in-teams.md) ausführliche Informationen und Links zu schrittweisen Bereitstellungsartikeln.</span><span class="sxs-lookup"><span data-stu-id="e82a2-252">When you are ready for production deployment of secure SharePoint Online sites, see [Secure SharePoint Online sites and files](secure-files-in-teams.md) for detailed information and links to step-by-step deployment articles.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e82a2-253">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e82a2-253">See Also</span></span>

[<span data-ttu-id="e82a2-254">Cloudakzeptanz und Hybridlösungen</span><span class="sxs-lookup"><span data-stu-id="e82a2-254">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
