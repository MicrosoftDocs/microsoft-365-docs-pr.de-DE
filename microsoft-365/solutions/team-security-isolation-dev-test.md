---
title: Konfigurieren eines Teams mit Sicherheitsisolierung in einer Entwicklungs-/Testumgebung
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom: ''
description: Konfigurieren Sie Sicherheit und Infrastruktur, die es Ihren Mitarbeitern ermöglicht, von überall und jederzeit remote zu arbeiten.
ms.openlocfilehash: 62361126ad0b843fd909b98807eeb186f13e75bb
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778339"
---
# <a name="configure-a-team-with-security-isolation-in-a-devtest-environment"></a><span data-ttu-id="01f20-103">Konfigurieren eines Teams mit Sicherheitsisolierung in einer Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="01f20-103">Configure a team with security isolation in a dev/test environment</span></span>

<span data-ttu-id="01f20-104">Dieser Artikel enthält eine Schritt-für-Schritt-Anleitung zum Erstellen eines [Teams mit Sicherheitsisolierung](secure-teams-security-isolation.md) in einer Entwicklungs-/Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="01f20-104">This article provides step-by-step instructions to create a [team with security isolation](secure-teams-security-isolation.md) in a dev/test environment.</span></span>

![Konfiguration für das isolierte Team „Unternehmensstrategie“](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

<span data-ttu-id="01f20-106">Verwenden Sie diese Entwicklungs-/Testumgebung zum Experimentieren und zur Feinabstimmung der Einstellungen für Ihre spezifischen Bedürfnisse, bevor Sie diese Art von Team in der Produktion einsetzen.</span><span class="sxs-lookup"><span data-stu-id="01f20-106">Use this dev/test environment to experiment and fine-tune settings for your specific needs before deploying this type of team in production.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="01f20-107">Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="01f20-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="01f20-108">Wenn Sie vertrauliche und streng vertrauliche Teams auf einfache Weise mit Minimalanforderungen testen möchten, befolgen Sie die Anweisungen unter [Einfache Basiskonfiguration](../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="01f20-108">If you just want to test sensitive and highly sensitive teams in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="01f20-109">Wenn Sie vertrauliche und hochgradig vertrauliche Teams in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung](../enterprise/password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="01f20-109">If you want to test sensitive and highly sensitive teams in a simulated enterprise, follow the instructions in [Password hash synchronization](../enterprise/password-hash-sync-m365-ent-test-environment.md).</span></span>

>[!Note]
><span data-ttu-id="01f20-110">Das Testen eines Teams mit Sicherheitsisolierung erfordert nicht die simulierte Unternehmenstestumgebung, die ein simuliertes, mit dem Internet verbundenes Intranet und die Verzeichnissynchronisierung für eine Active Directory Domain Services (AD DS)-Struktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="01f20-110">Testing a team with security isolation does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="01f20-111">Dies wird hier als Option bereitgestellt, damit Sie ein Team mit Sicherheitsisolation testen und damit in einer Umgebung, die eine typische Organisation darstellt, experimentieren können.</span><span class="sxs-lookup"><span data-stu-id="01f20-111">It is provided here as an option so that you can test a team with security isolation and experiment with it in an environment that represents a typical organization.</span></span>
>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-azure-ad-group-and-users"></a><span data-ttu-id="01f20-112">Phase 2: Azure Active Directory (Azure AD)-Gruppe und -Benutzende erstellen und konfigurieren</span><span class="sxs-lookup"><span data-stu-id="01f20-112">Phase 2: Create and configure your Azure Active Directory (Azure AD) group and users</span></span>

<span data-ttu-id="01f20-113">In dieser Phase erstellen und konfigurieren Sie eine Azure AD-Gruppe und -Benutzer für eine fiktive Organisation.</span><span class="sxs-lookup"><span data-stu-id="01f20-113">In this phase, you create and configure an Azure AD group and users for your fictional organization.</span></span>
  
<span data-ttu-id="01f20-114">Erstellen Sie zunächst eine Sicherheitsgruppe mit dem Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="01f20-114">First, create a security group with the Azure portal.</span></span>
  
1. <span data-ttu-id="01f20-115">Erstellen Sie eine separate Registerkarte in Ihrem Browser, und wechseln Sie dann zum Azure-Portal unter [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="01f20-115">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span> <span data-ttu-id="01f20-116">Falls erforderlich, melden Sie sich mit den Anmeldeinformationen des globalen Administratorkontos für Ihr Microsoft 365 E5-Testabonnement oder Ihr kostenpflichtiges Abonnement an.</span><span class="sxs-lookup"><span data-stu-id="01f20-116">If needed, sign in with the credentials of the global administrator account for your Microsoft 365 E5 trial or paid subscription.</span></span>
    
2. <span data-ttu-id="01f20-117">Klicken Sie im Azure-Portal auf **Azure Active Directory > Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-117">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="01f20-118">Klicken Sie auf dem Blatt **Gruppen - Alle Gruppen** auf **+ Neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="01f20-118">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="01f20-119">Auf dem Blatt **Gruppe**:</span><span class="sxs-lookup"><span data-stu-id="01f20-119">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="01f20-120">Wählen Sie unter **Gruppentyp** die Option **Sicherheit** aus.</span><span class="sxs-lookup"><span data-stu-id="01f20-120">Select **Security** in **Group type**.</span></span>
    
  - <span data-ttu-id="01f20-121">Geben **C-Suite** unter **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="01f20-121">Type **C-Suite** in **Name**.</span></span>
    
  - <span data-ttu-id="01f20-122">Wählen Sie **Zugewiesen** unter **Mitgliedschaftstyp** aus.</span><span class="sxs-lookup"><span data-stu-id="01f20-122">Select **Assigned** in **Membership type**.</span></span>
      
5. <span data-ttu-id="01f20-123">Klicken Sie auf **Erstellen**, und schließen Sie dann das Blatt **Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="01f20-123">Click **Create**, and then close the **Group** blade.</span></span>
    
<span data-ttu-id="01f20-124">Konfigurieren Sie als Nächstes die automatische Lizenzierung so, dass den Mitgliedern der neuen **C-Suite**-Gruppe automatisch eine Microsoft 365 E5-Lizenz zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="01f20-124">Next, configure automatic licensing so that members of the new **C-Suite** group are automatically assigned a Microsoft 365 E5 license.</span></span>
  
1. <span data-ttu-id="01f20-125">Klicken Sie im Azure-Portal auf **Azure Active Directory > Lizenzen > Alle Produkte**.</span><span class="sxs-lookup"><span data-stu-id="01f20-125">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>
    
2. <span data-ttu-id="01f20-126">Wählen Sie in der Liste **Microsoft 365 Enterprise E5** aus, und klicken Sie dann auf **Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-126">In the list, select **Microsoft 365 Enterprise E5**, and then click **Assign**.</span></span>
    
3. <span data-ttu-id="01f20-127">Klicken Sie auf dem Blatt **Lizenz zuweisen** auf **Benutzer und Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-127">In the **Assign license** blade, click **Users and groups**.</span></span>
    
4. <span data-ttu-id="01f20-128">Wählen Sie in der Liste der Gruppen die Gruppe **C-Suite** aus.</span><span class="sxs-lookup"><span data-stu-id="01f20-128">In the list of groups, select the **C-Suite** group.</span></span>
    
5. <span data-ttu-id="01f20-129">Klicken Sie auf **Auswählen** und dann auf **Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-129">Click **Select**, and then click **Assign**.</span></span>
    
6. <span data-ttu-id="01f20-130">Schließen Sie die Registerkarte für das Azure Portal in Ihrem Browser.</span><span class="sxs-lookup"><span data-stu-id="01f20-130">Close the Azure portal tab in your browser.</span></span>
    
<span data-ttu-id="01f20-131">Als Nächstes, [stellen Sie eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul her](../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="01f20-131">Next, [connect with the Azure Active Directory PowerShell for Graph module](../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="01f20-132">Geben Sie den Namen Ihrer Organisation, Ihren Standort und ein gemeinsames Kennwort ein, und führen Sie dann die folgenden Befehle über die PowerShell-Eingabeaufforderung oder in der ISE-Umgebung (Integrated Script Environment) aus, um neue Benutzerkonten zu erstellen und sie zu der C-Suite-Gruppe hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="01f20-132">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create new user accounts and add them to the C-Suite group:</span></span>
  
```powershell
$orgName="<organization name, such as contoso-test for the contoso-test.onmicrosoft.com trial subscription domain name>"
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
```

> [!NOTE]
> <span data-ttu-id="01f20-133">Für die Automatisierung und Vereinfachung der Konfiguration einer Dev/Test-Umgebung wird hier ein gemeinsames Kennwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="01f20-133">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="01f20-134">Natürlich ist davon bei Produktionsabonnements dringend abzuraten.</span><span class="sxs-lookup"><span data-stu-id="01f20-134">Obviously, this is highly discouraged for production subscriptions.</span></span> 
  
<span data-ttu-id="01f20-135">Gehen Sie folgendermaßen vor, um sicherzustellen, dass die gruppenbasierte Lizenzierung ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="01f20-135">Use these steps to verify that group-based licensing is working correctly.</span></span>
  
1. <span data-ttu-id="01f20-136">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="01f20-136">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="01f20-137">Klicken Sie auf der neuen Registerkarte **Microsoft 365 Admin Center** des Browsers auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="01f20-137">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>
    
3. <span data-ttu-id="01f20-138">Klicken Sie in der Liste der Benutzer auf **CEO**.</span><span class="sxs-lookup"><span data-stu-id="01f20-138">In the list of users, click **CEO**.</span></span>
    
4. <span data-ttu-id="01f20-139">Stellen Sie im Bereich, der die Eigenschaften des Benutzerkontos **CEO** anzeigt, sicher, dass ihm die Lizenz **Microsoft 365 Enterprise E5** in **Produktlizenzen** zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="01f20-139">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Microsoft 365 Enterprise E5** license in **Product licenses**.</span></span>
    
## <a name="phase-3-create-your-team"></a><span data-ttu-id="01f20-140">Phase 3: Erstellen Ihres Teams</span><span class="sxs-lookup"><span data-stu-id="01f20-140">Phase 3: Create your team</span></span>

<span data-ttu-id="01f20-141">In dieser Phase erstellen und konfigurieren Sie ein Team mit Sicherheitsisolierung, in dem die Mitglieder des leitenden Führungsteams an der Unternehmensstrategie mitarbeiten.</span><span class="sxs-lookup"><span data-stu-id="01f20-141">In this phase, you create and configure a team with security isolation for members of the senior leadership team to collaborate on company strategy.</span></span>

<span data-ttu-id="01f20-142">Aktivieren Sie zunächst Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Office 365-Gruppen und SharePoint-Websites, bevor Sie mit den Schritten in [diesem Artikel](../compliance/sensitivity-labels-teams-groups-sites.md) fortfahren.</span><span class="sxs-lookup"><span data-stu-id="01f20-142">First, enable sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites before you proceed with the steps in [this article](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="01f20-143">Als Nächstes, erstellen Sie das Team:</span><span class="sxs-lookup"><span data-stu-id="01f20-143">Next, create the team:</span></span>

1. <span data-ttu-id="01f20-144">Klicken Sie in Microsoft Teams auf der linken Seite auf **Teams** und dann unten in der Teamliste auf **Einem Team beitreten oder ein Team erstellen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-144">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="01f20-145">Klicken Sie auf **Team erstellen** (erste Karte, obere linke Ecke).</span><span class="sxs-lookup"><span data-stu-id="01f20-145">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="01f20-146">Wählen Sie **Neuerstellen eines Teams**.</span><span class="sxs-lookup"><span data-stu-id="01f20-146">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="01f20-147">Behalten Sie in der Liste **Vertraulichkeit** die Standardeinstellung bei.</span><span class="sxs-lookup"><span data-stu-id="01f20-147">In the **Sensitivity** list, keep the default.</span></span>
5. <span data-ttu-id="01f20-148">Klicken Sie unter **Datenschutz** auf **Privat**.</span><span class="sxs-lookup"><span data-stu-id="01f20-148">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="01f20-149">Geben Sie **Unternehmensstrategie** ein, und klicken Sie dann auf **Erstellen** > **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-149">Type **Company Strategy**, and then click **Create** > **Close**.</span></span>

<span data-ttu-id="01f20-150">Beschränken Sie als nächstes die Schaffung privater Kanäle auf die Eigentümer der Unternehmensstrategie-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="01f20-150">Next, restrict the creation of private channels to owners of the Company Strategy group.</span></span>

1. <span data-ttu-id="01f20-151">Klicken Sie im Team auf **Weitere Optionen** und dann auf **Team verwalten**.</span><span class="sxs-lookup"><span data-stu-id="01f20-151">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="01f20-152">Erweitern Sie auf der Registerkarte **Einstellungen** den Eintrag **Mitgliedsberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-152">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="01f20-153">Deaktivieren Sie das Kontrollkästchen **Mitglieder können private Kanäle erstellen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-153">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="01f20-154">Konfigurieren Sie als nächstes eine Vertraulichkeitsbezeichnung mit den folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="01f20-154">Next, you need to configure a sensitivity label with the following settings:</span></span>

- <span data-ttu-id="01f20-155">Der Name lautet "Unternehmensstrategie".</span><span class="sxs-lookup"><span data-stu-id="01f20-155">The name is Company Strategy</span></span>
- <span data-ttu-id="01f20-156">Die Verschlüsselung ist aktiviert.</span><span class="sxs-lookup"><span data-stu-id="01f20-156">Encryption is enabled</span></span>
- <span data-ttu-id="01f20-157">Die Gruppe „Unternehmensstrategie“ verfügt über Berechtigungen für die gemeinsame Dokumenterstellung.</span><span class="sxs-lookup"><span data-stu-id="01f20-157">The Company Strategy group has Co-Author permissions</span></span>

<span data-ttu-id="01f20-158">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="01f20-158">Follow these steps:</span></span>

1. <span data-ttu-id="01f20-159">Öffnen Sie das [Microsoft 365 Compliance Center](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="01f20-159">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="01f20-160">Klicken Sie unter **Lösungen**auf **Informationsschutz**.</span><span class="sxs-lookup"><span data-stu-id="01f20-160">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="01f20-161">Klicken Sie auf **Bezeichnung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-161">Click **Create a label**.</span></span>
4. <span data-ttu-id="01f20-162">Geben Sie **Unternehmensstrategie** für den Bezeichnungsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="01f20-162">Type **Company Strategy** for the label name.</span></span>
5. <span data-ttu-id="01f20-163">Geben Sie als QuickInfo **Dokumente zur Unternehmensstrategie für leitende Angestellte** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="01f20-163">Type **Senior leadership company strategy documents** as the tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="01f20-164">Wählen Sie auf der Seite **Verschlüsselung** im Dropdownmenü **Verschlüsselung** **Anwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="01f20-164">On the **Encryption** page, in the **Encryption** dropdown, choose **Apply**.</span></span>
7. <span data-ttu-id="01f20-165">Hinzufügen der Team-Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="01f20-165">To add the team permissions:</span></span><br>
  <span data-ttu-id="01f20-166">a.</span><span class="sxs-lookup"><span data-stu-id="01f20-166">a.</span></span> <span data-ttu-id="01f20-167">Klicken Sie auf **Zuweisen von Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-167">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="01f20-168">b.</span><span class="sxs-lookup"><span data-stu-id="01f20-168">b.</span></span> <span data-ttu-id="01f20-169">Klicken Sie auf **Benutzer oder Gruppen hinzufügen**, wählen Sie **Unternehmensstrategie** aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-169">Click **Add users or groups**, select **Company Strategy**, and then click **Add**.</span></span><br>
  <span data-ttu-id="01f20-170">c.</span><span class="sxs-lookup"><span data-stu-id="01f20-170">c.</span></span> <span data-ttu-id="01f20-171">Klicken Sie auf **Berechtigungen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-171">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="01f20-172">d.</span><span class="sxs-lookup"><span data-stu-id="01f20-172">d.</span></span> <span data-ttu-id="01f20-173">Wählen Sie in der Dropdownliste **Mitautor**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="01f20-173">Choose **Co-Author** from the dropdown list, and then click **Save**.</span></span><br>
8. <span data-ttu-id="01f20-174">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="01f20-174">Click **Next**.</span></span>
9. <span data-ttu-id="01f20-175">Klicken Sie auf der Seite **Inhaltskennzeichnung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="01f20-175">On the **Content marking** page, click **Next**.</span></span>
10. <span data-ttu-id="01f20-176">Legen Sie auf der Seite **Website- und Gruppeneinstellungen** die Option **Website- und Gruppeneinstellungen** auf **Ein** fest.</span><span class="sxs-lookup"><span data-stu-id="01f20-176">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
11. <span data-ttu-id="01f20-177">Wählen Sie in der Dropdownliste **Datenschutz für mit Office 365-Gruppen verbundene Teamwebsites** die Option **Privat – nur Mitglieder können auf die Website zugreifen** aus.</span><span class="sxs-lookup"><span data-stu-id="01f20-177">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
12. <span data-ttu-id="01f20-178">Wählen Sie unter **Nicht verwaltete Geräte** die Option **Zugriff blockieren**.</span><span class="sxs-lookup"><span data-stu-id="01f20-178">Under **Unmanaged devices**, choose **Block access**.</span></span>
13. <span data-ttu-id="01f20-179">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="01f20-179">Click **Next**.</span></span>
14. <span data-ttu-id="01f20-180">Klicken Sie auf der Seite **Automatisches Bezeichnen für Office-Apps** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="01f20-180">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
15. <span data-ttu-id="01f20-181">Klicken Sie auf **Absenden** und anschließend auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="01f20-181">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="01f20-182">Als Nächstes, veröffentlichen Sie die neue Bezeichnung mit diesen Schritten:</span><span class="sxs-lookup"><span data-stu-id="01f20-182">Next, publish the new label with these steps:</span></span> 

1. <span data-ttu-id="01f20-183">Wählen Sie im Microsoft 365 Compliance Center auf der Seite **Informationsschutz** die Registerkarte **Bezeichnungsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="01f20-183">In the Microsoft 365 compliance center, on the **Information protection** page, choose the **Label policies** tab.</span></span>
2. <span data-ttu-id="01f20-184">Klicken Sie auf **Bezeichnungen veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-184">Click **Publish labels**.</span></span>
3. <span data-ttu-id="01f20-185">Klicken Sie auf der Seite **Zu veröffentlichende Vertraulichkeitsbezeichnungen wählen** auf **Zu veröffentlichende Vertraulichkeitsbezeichnungen wählen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-185">On the **Choose sensitivity labels to publish** page, click **Choose sensitivity labels to publish**.</span></span>
4. <span data-ttu-id="01f20-186">Wählen Sie **Unternehmensstrategie** aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-186">Select **Company Strategy**, and then click **Add**.</span></span>
5. <span data-ttu-id="01f20-187">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="01f20-187">Click **Next**.</span></span>
6. <span data-ttu-id="01f20-188">Klicken Sie auf der Seite **Für Benutzer und Gruppen veröffentlichen** auf **Benutzer und Gruppen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-188">On the **Publish to users and groups** page, click **Choose users and groups**.</span></span>
7. <span data-ttu-id="01f20-189">Klicken Sie auf **Hinzufügen**, und wählen Sie dann **Unternehmensstrategie** aus.</span><span class="sxs-lookup"><span data-stu-id="01f20-189">Click **Add**, and then select **Company Strategy**.</span></span>
8. <span data-ttu-id="01f20-190">Klicken Sie auf **Hinzufügen** und dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="01f20-190">Click **Add**, and then click **Done**.</span></span>
9. <span data-ttu-id="01f20-191">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="01f20-191">Click **Next**.</span></span>
10. <span data-ttu-id="01f20-192">Aktivieren Sie auf der Seite Richtlinieneinstellungen das Kontrollkästchen **Benutzer müssen eine Begründung für das Entfernen einer Bezeichnung oder einer Bezeichnung mit niedrigerer Klassifizierung angeben**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="01f20-192">On the Policy settings page, select the **Users must provide justification to remove a label or lower classification label** check box, and then click **Next**.</span></span>
11. <span data-ttu-id="01f20-193">Geben Sie **Unternehmensstrategie** für den Richtliniennamen ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="01f20-193">Type **Company Strategy** for the policy name, and then click **Next**.</span></span>
12. <span data-ttu-id="01f20-194">Klicken Sie auf **Absenden** und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="01f20-194">Click **Submit** and then click **Done**.</span></span>

<span data-ttu-id="01f20-195">Es kann einige Zeit dauern, bis die Bezeichnung **Unternehmensstrategie** nach ihrer Veröffentlichung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="01f20-195">It may take some time for the **Company Strategy** label to become available after it's been published.</span></span>

<span data-ttu-id="01f20-196">Als Nächstes wenden Sie Ihre neue Bezeichnung auf das Team für **Unternehmensstrategie** an und aktualisieren den standardmäßigen Linktyp für die Freigabe, um das Risiko zu verringern, dass Dateien und Ordner versehentlich für ein breiteres Publikum freigegeben werden als beabsichtigt.</span><span class="sxs-lookup"><span data-stu-id="01f20-196">Next, apply your new label to the **Company Strategy** team and update the default sharing link type to reduce the risk of accidentally sharing files and folders to a wider audience than intended.</span></span> 

1. <span data-ttu-id="01f20-197">Öffnen Sie das [SharePoint Admin Center](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="01f20-197">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="01f20-198">Klicken Sie unter **Websites** auf **Aktive Websites**.</span><span class="sxs-lookup"><span data-stu-id="01f20-198">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="01f20-199">Klicken Sie auf die Website **Unternehmensstrategie**.</span><span class="sxs-lookup"><span data-stu-id="01f20-199">Click the **Company Strategy** site.</span></span>
4. <span data-ttu-id="01f20-200">Klicken Sie auf der Registerkarte **Richtlinien** unter **Vertraulichkeit** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="01f20-200">On the **Policies** tab, under **Sensitivity**, click **Edit**.</span></span>
5. <span data-ttu-id="01f20-201">Wählen Sie die Bezeichnung **Unternehmensstrategie** aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="01f20-201">Select the **Company Strategy** label, and then click **Save**.</span></span>
6. <span data-ttu-id="01f20-202">Klicken Sie auf der Registerkarte **Richtlinien** unter **Externe Freigabe** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="01f20-202">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="01f20-203">Wählen Sie **Nur Personen in Ihrer Organisation**.</span><span class="sxs-lookup"><span data-stu-id="01f20-203">Choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="01f20-204">Deaktivieren Sie unter **Standardmäßiger Freigabe**-Linktyp das Kontrollkästchen **Identisch mit der Einstellung auf Organisationsebene**, und wählen Sie **Personen mit vorhandenem Zugriff** aus.</span><span class="sxs-lookup"><span data-stu-id="01f20-204">Under **Default sharing** link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="01f20-205">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="01f20-205">Click **Save**.</span></span>

<span data-ttu-id="01f20-206">Als Nächstes, konfigurieren Sie die Websitefreigabe nur für Besitzer für das Team **Unternehmensstrategie**.</span><span class="sxs-lookup"><span data-stu-id="01f20-206">Next, configure owners-only site sharing for the **Company Strategy** team.</span></span>

1. <span data-ttu-id="01f20-207">Gehen Sie in Teams zur Registerkarte **Allgemein** des Teams **Unternehmensstrategie**.</span><span class="sxs-lookup"><span data-stu-id="01f20-207">In Teams, navigate to the **General** tab of the **Company Strategy** team.</span></span>
2. <span data-ttu-id="01f20-208">Klicken Sie auf der Symbolleiste des Teams auf **Dateien**.</span><span class="sxs-lookup"><span data-stu-id="01f20-208">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="01f20-209">Klicken Sie auf die drei Punkte "(…)" und dann auf **In SharePoint öffnen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-209">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="01f20-210">Klicken Sie in der Symbolleiste der zugrunde liegenden SharePoint-Website auf das Symbol "Einstellungen" und anschließend auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-210">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="01f20-211">Klicken Sie im Bereich „Websiteberechtigungen“ unter **Websitefreigabe** auf **Freigabemethode für Mitglieder ändern**.</span><span class="sxs-lookup"><span data-stu-id="01f20-211">In the Site permissions pane, under **Site Sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="01f20-212">Wählen Sie unter **Freigabeberechtigungen** die Option **Nur Websitebesitzer können Dateien, Ordner und die Website teilen** aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="01f20-212">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>
7. <span data-ttu-id="01f20-213">Schließen Sie die Bereiche **Berechtigungen** und **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="01f20-213">Close the **Permissions** and **Settings** panes.</span></span>

<span data-ttu-id="01f20-214">Wenn Sie sich als Mitglied der Gruppe „Unternehmensstrategie“ anmelden, wird **Unternehmensstrategie** auf der Symbolleiste „Start“ in Word, Excel und PowerPoint unter der Option **Vertraulichkeit** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="01f20-214">If you sign in as a member of the Company Strategy group, you will see **Company Strategy** in the **Sensitivity** option in the Home toolbar of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="01f20-215">Wählen Sie unter der Option **Vertraulichkeit** die Bezeichnung **Unternehmensstrategie** aus, um einer Datei eine Bezeichnung zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="01f20-215">Select the **Company Strategy** label from the **Sensitivity** option to assign the label to a file.</span></span>

<span data-ttu-id="01f20-216">Hier ist die resultierende Konfiguration für das Unternehmensstrategieteam.</span><span class="sxs-lookup"><span data-stu-id="01f20-216">Here is the resulting configuration for the Company Strategy team.</span></span>

![Konfiguration für das isolierte Team „Unternehmensstrategie“](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

## <a name="next-step"></a><span data-ttu-id="01f20-218">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="01f20-218">Next step</span></span>

<span data-ttu-id="01f20-219">Wenn Sie für den Produktionseinsatz bereit sind, lesen Sie diese [Konfigurationsanweisungen](secure-teams-security-isolation.md).</span><span class="sxs-lookup"><span data-stu-id="01f20-219">When you're ready for production deployment, see these [configuration instructions](secure-teams-security-isolation.md).</span></span>
