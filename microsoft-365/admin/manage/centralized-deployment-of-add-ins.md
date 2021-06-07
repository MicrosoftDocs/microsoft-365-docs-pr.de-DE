---
title: Ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Ermitteln Sie, ob Ihr Mandant und Ihre Benutzer die Anforderungen erfüllen, damit Sie die zentrale Bereitstellung verwenden können, um Office-Add-Ins bereitzustellen.
ms.openlocfilehash: 63775ed6bab2d595ae87085e1607be5818b355e2
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782486"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="41022-103">Ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert</span><span class="sxs-lookup"><span data-stu-id="41022-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="41022-104">Die zentrale Bereitstellung ist die empfohlene und funktionsreichere Möglichkeit für die meisten Kunden, Office-Add-Ins für Benutzer und Gruppen in Ihrer Organisation bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="41022-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="41022-105">Wenn Sie ein Administrator sind, verwenden Sie diese Anleitung, um festzustellen, ob Ihre Organisation und Ihre Benutzer die Anforderungen erfüllen, damit Sie die zentrale Bereitstellung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="41022-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="41022-106">Die zentrale Bereitstellung bietet die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="41022-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="41022-107">Ein globaler Administrator kann ein Add-In direkt einem Benutzer, mehreren Benutzern über eine Gruppe oder allen Benutzern in der Organisation zuweisen.</span><span class="sxs-lookup"><span data-stu-id="41022-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="41022-108">Wenn die relevante Office Anwendung gestartet wird, wird das Add-In automatisch heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="41022-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="41022-109">Wenn das Add-In Add-In-Befehle unterstützt, wird das Add-In automatisch im Menüband innerhalb der Office-Anwendung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="41022-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="41022-110">Add-Ins werden für Benutzer nicht mehr angezeigt, wenn der Administrator das Add-In deaktiviert oder löscht oder wenn der Benutzer aus Azure Active Directory oder aus einer Gruppe entfernt wird, der das Add-In zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="41022-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="41022-111">Die zentrale Bereitstellung unterstützt drei Desktopplattformen Windows, Mac- und Online-Office-Apps.</span><span class="sxs-lookup"><span data-stu-id="41022-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="41022-112">Die zentrale Bereitstellung unterstützt auch iOS und Android (nur Outlook mobile Add-Ins).</span><span class="sxs-lookup"><span data-stu-id="41022-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="41022-113">Es kann bis zu 24 Stunden dauern, bis ein Add-In für alle Benutzer für den Client angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="41022-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="41022-114">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="41022-114">Before you begin</span></span>

<span data-ttu-id="41022-115">Die zentrale Bereitstellung von Add-Ins erfordert, dass die Benutzer Microsoft 365 Enterprise SKUs verwenden: E3/E5/F3 oder Business SKUs: Business Basic, Business Standard, Business Premium (und mit ihrer Organisations-ID bei Office angemeldet sind) und über Exchange Online und aktive Exchange Online Postfächer verfügen.</span><span class="sxs-lookup"><span data-stu-id="41022-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="41022-116">Ihr Abonnementverzeichnis muss sich entweder in Azure Active Directory befinden oder mit Azure Active Directory verbunden sein.</span><span class="sxs-lookup"><span data-stu-id="41022-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="41022-117">Sie können die spezifischen Anforderungen für Office und Exchange unten anzeigen oder die [zentralisierte Kompatibilitätsprüfung](#centralized-deployment-compatibility-checker)für die Bereitstellung verwenden.</span><span class="sxs-lookup"><span data-stu-id="41022-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="41022-118">Folgendes wird von der zentralen Bereitstellung nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="41022-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="41022-119">Add-Ins, die Word, Excel oder PowerPoint in Office 2013 zum Ziel haben</span><span class="sxs-lookup"><span data-stu-id="41022-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="41022-120">Ein lokaler Verzeichnisdienst</span><span class="sxs-lookup"><span data-stu-id="41022-120">An on-premises directory service</span></span>
- <span data-ttu-id="41022-121">Add-In-Bereitstellung in einem Exchange lokalen Postfach</span><span class="sxs-lookup"><span data-stu-id="41022-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="41022-122">Add-In-Bereitstellung in SharePoint</span><span class="sxs-lookup"><span data-stu-id="41022-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="41022-123">Teams-Apps</span><span class="sxs-lookup"><span data-stu-id="41022-123">Teams apps</span></span>
- <span data-ttu-id="41022-124">Bereitstellung von COM-Add-Ins (Component Object Model) oder Visual Studio-Tools für Office-Add-Ins (VSTO).</span><span class="sxs-lookup"><span data-stu-id="41022-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="41022-125">Bereitstellungen von Microsoft 365, die keine Exchange Online wie z. B. SKUs enthalten: Microsoft 365 Apps for Business und Microsoft 365 Apps für Enterprise.</span><span class="sxs-lookup"><span data-stu-id="41022-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="41022-126">Office Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41022-126">Office Requirements</span></span>

- <span data-ttu-id="41022-127">Für Word-, Excel- und PowerPoint-Add-Ins müssen Ihre Benutzer eine der folgenden Optionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="41022-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="41022-128">Auf einem Windows Gerät, Version 1704 oder höher von Microsoft 365 Enterprise SKUs: E3/E5/F3 oder Business SKUs: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="41022-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="41022-129">Auf einem Mac, Version 15.34 oder höher.</span><span class="sxs-lookup"><span data-stu-id="41022-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="41022-130">Für Outlook müssen Ihre Benutzer eine der folgenden Optionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="41022-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="41022-131">Version 1701 oder höher von Microsoft 365 Enterprise SKUs: E3/E5/F3 oder Business SKUs: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="41022-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="41022-132">Version 1808 oder höher von Office Professional Plus 2019 oder Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="41022-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="41022-133">Version 16.0.4494.1000 oder höher von Office Professional Plus 2016 (MSI) oder Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="41022-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="41022-134">Version 15.0.4937.1000 oder höher von Office Professional Plus 2013 (MSI) oder Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="41022-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="41022-135">Version 16.0.9318.1000 oder höher von Office 2016 für Mac</span><span class="sxs-lookup"><span data-stu-id="41022-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="41022-136">Version 2.75.0 oder höher von Outlook Mobile für iOS</span><span class="sxs-lookup"><span data-stu-id="41022-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="41022-137">Version 2.2.145 oder höher von Outlook Mobile für Android</span><span class="sxs-lookup"><span data-stu-id="41022-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="41022-138">\*MSI-Versionen von Outlook zeigen vom Administrator installierte Add-Ins im entsprechenden Outlook Menüband an, nicht im Abschnitt "Meine Add-Ins".</span><span class="sxs-lookup"><span data-stu-id="41022-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="41022-139">Exchange Online Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41022-139">Exchange Online requirements</span></span>

<span data-ttu-id="41022-140">Microsoft Exchange speichert die Add-In-Manifeste im Mandanten Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="41022-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="41022-141">Der Administrator, der Add-Ins bereitstellt, und die Benutzer, die diese Add-Ins erhalten, müssen eine Version von Exchange Online verwenden, die die OAuth-Authentifizierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="41022-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="41022-p106">Informieren Sie sich beim Exchange-Administrator Ihrer Organisation, um herauszufinden, welche Konfiguration verwendet wird. Die OAuth-Verbindung pro Benutzer kann überprüft werden, indem Sie das PowerShell-Cmdlet [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) verwenden.</span><span class="sxs-lookup"><span data-stu-id="41022-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="41022-144">Kompatibilitätsprüfung für die zentrale Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="41022-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="41022-145">Mithilfe der Kompatibilitätsprüfung für die zentrale Bereitstellung können Sie überprüfen, ob die Benutzer in Ihrem Mandanten für die Verwendung der zentralen Bereitstellung für Word, Excel und PowerPoint eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="41022-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="41022-146">Die Kompatibilitätsprüfung ist für die Unterstützung von Outlook nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="41022-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="41022-147">Laden Sie die [Kompatibilitätsprüfung herunter.](https://aka.ms/officeaddindeploymentorgcompatibilitychecker)</span><span class="sxs-lookup"><span data-stu-id="41022-147">Download the [compatibility checker](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="41022-148">Ausführen der Kompatibilitätsprüfung</span><span class="sxs-lookup"><span data-stu-id="41022-148">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="41022-149">Starten Sie ein Fenster mit erhöhten PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="41022-149">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="41022-150">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="41022-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="41022-151">Führen Sie den Befehl **Invoke-CompatabilityCheck aus:**</span><span class="sxs-lookup"><span data-stu-id="41022-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="41022-152">Dieser Befehl fordert Sie zur Eingabe von  *_TenantDomain_* auf (z. B. *TailspinToysIncorporated.onmicrosoft). </span> com*) und  *_TenantAdmin-Anmeldeinformationen_* (verwenden Sie Ihre globalen Administratoranmeldeinformationen), und fordern Sie dann die Zustimmung an.</span><span class="sxs-lookup"><span data-stu-id="41022-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="41022-153">Je nach Anzahl der Benutzer Ihres Mandanten kann die Prüfung nach Minuten oder Stunden abgeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="41022-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="41022-154">Sobald die Ausführung des Tools abgeschlossen ist, wird eine Ausgabedatei im CSV-Format (durch Trennzeichen getrenntes Format) erzeugt.</span><span class="sxs-lookup"><span data-stu-id="41022-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="41022-155">Die Datei wird standardmäßig in **C:\windows\system32** gespeichert.</span><span class="sxs-lookup"><span data-stu-id="41022-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="41022-156">Die Ausgabedatei enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="41022-156">The output file contains the following information:</span></span>
  
- <span data-ttu-id="41022-157">Benutzername</span><span class="sxs-lookup"><span data-stu-id="41022-157">User Name</span></span>
    
- <span data-ttu-id="41022-158">Benutzer-ID (E-Mail-Adresse des Benutzers)</span><span class="sxs-lookup"><span data-stu-id="41022-158">User ID (User's email address)</span></span>
    
- <span data-ttu-id="41022-159">Zentrale Bereitstellung bereit - Wenn die übrigen Punkte zutreffen</span><span class="sxs-lookup"><span data-stu-id="41022-159">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="41022-160">Office Plan – Der Plan für Office, für den sie lizenziert sind</span><span class="sxs-lookup"><span data-stu-id="41022-160">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="41022-161">Office aktiviert - Wenn Office aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="41022-161">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="41022-162">Unterstütztes Postfach - Wenn das Postfach für OAuth aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="41022-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="41022-163">Die mehrstufige Authentifizierung wird bei Verwendung des PowerShell-Moduls für die zentrale Bereitstellung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="41022-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span> <span data-ttu-id="41022-164">Das Modul funktioniert nur mit der Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="41022-164">The module only works with Basic authentication.</span></span>
  
## <a name="user-and-group-assignments"></a><span data-ttu-id="41022-165">Benutzer- und Gruppenzuordnungen</span><span class="sxs-lookup"><span data-stu-id="41022-165">User and group assignments</span></span>

<span data-ttu-id="41022-166">Das Feature für die zentrale Bereitstellung unterstützt derzeit die Mehrzahl der von Azure Active Directory unterstützten Gruppen, einschließlich Microsoft 365 Gruppen, Verteilerlisten und Sicherheitsgruppen.</span><span class="sxs-lookup"><span data-stu-id="41022-166">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="41022-167">Nicht für E-Mail aktivierte Sicherheitsgruppen werden derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="41022-167">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="41022-168">Die zentrale Bereitstellung unterstützt Zuweisungen zu einzelnen Benutzern, Gruppen und allen Personen im Mandanten.</span><span class="sxs-lookup"><span data-stu-id="41022-168">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="41022-169">Die zentrale Bereitstellung unterstützt Benutzer in Gruppen der oberen Ebene oder Gruppen ohne übergeordnete Gruppen, jedoch keine Benutzer in geschachtelten Gruppen oder Gruppen, die über übergeordnete Gruppen verfügen.</span><span class="sxs-lookup"><span data-stu-id="41022-169">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="41022-p111">Schauen Sie sich das folgende Beispiel an, in dem Sandra, Sofia und die Gruppe "Vertriebsabteilung" einem Add-In zugeordnet werden. Da es sich bei "Vertriebsabteilung Westküste" um eine geschachtelte Gruppe handelt, werden Bert und Fred keinem Add-In zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="41022-p111">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagramm der Vertriebsabteilung](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="41022-173">Herausfinden, ob eine Gruppe geschachelte Gruppen enthält</span><span class="sxs-lookup"><span data-stu-id="41022-173">Find out if a group contains nested groups</span></span>

<span data-ttu-id="41022-174">Die einfachste Methode, um herauszufinden, ob eine Gruppe geschachtelte Gruppen enthält, besteht darin, in Outlook die Gruppenvisitenkarte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="41022-174">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="41022-175">Wenn Sie den Gruppennamen im Feld **"An"** einer E-Mail eingeben und dann bei der Auflösung den Gruppennamen auswählen, wird angezeigt, ob er Benutzer oder geschachtelte Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="41022-175">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="41022-176">Im nachfolgenden Beispiel werden auf der Registerkarte **Mitglieder** der Outlook-Visitenkarte der Testgruppe keine Benutzer und nur zwei Untergruppen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="41022-176">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Registerkarte "Mitglieder" Outlook Visitenkarte](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="41022-p113">Sie können die umgekehrte Abfrage durchführen, indem Sie die Gruppe auflösen, um zu sehen, ob sie Mitglied einer anderen Gruppe ist. Im Beispiel unten können Sie auf der Registerkarte **Mitgliedschaft** der Outlook-Visitenkarte sehen, dass Untergruppe 1 ein Mitglied der Testgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="41022-p113">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Registerkarte "Mitgliedschaft" der Visitenkarte Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="41022-p114">Alternativ können Sie die Azure Active Directory Graph-API verwenden, um Abfragen auszuführen, um die Liste der Gruppen innerhalb einer Gruppe zu finden. Weitere Informationen finden Sie unter [Vorgänge mit Gruppen | Graph-API-Referenz](/previous-versions/azure/ad/graph/api/groups-operations).</span><span class="sxs-lookup"><span data-stu-id="41022-p114">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](/previous-versions/azure/ad/graph/api/groups-operations).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="41022-183">Kontaktaufnahme mit dem Microsoft-Support</span><span class="sxs-lookup"><span data-stu-id="41022-183">Contacting Microsoft for support</span></span>

<span data-ttu-id="41022-184">Wenn probleme beim Laden des Add-Ins auftreten, während Sie Office Apps für das Web (Word, Excel usw.) verwenden, die zentral bereitgestellt wurden, müssen Sie sich möglicherweise an den Microsoft-Support wenden ([erfahren Sie, wie](../../business-video/get-help-support.md)).</span><span class="sxs-lookup"><span data-stu-id="41022-184">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../../business-video/get-help-support.md)).</span></span> <span data-ttu-id="41022-185">Geben Sie die folgenden Informationen zu Ihrer Microsoft 365 Umgebung im Supportticket an.</span><span class="sxs-lookup"><span data-stu-id="41022-185">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="41022-186">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="41022-186">**Platform**</span></span>|<span data-ttu-id="41022-187">**Debuginformationen**</span><span class="sxs-lookup"><span data-stu-id="41022-187">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="41022-188">Office</span><span class="sxs-lookup"><span data-stu-id="41022-188">Office</span></span>  <br/> | <span data-ttu-id="41022-189">Charles/Fiddler-Protokolle</span><span class="sxs-lookup"><span data-stu-id="41022-189">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="41022-190">Mandanten-ID ( [So wird's gemacht](/onedrive/find-your-office-365-tenant-id))</span><span class="sxs-lookup"><span data-stu-id="41022-190">Tenant ID ( [learn how](/onedrive/find-your-office-365-tenant-id))</span></span>  <br/>  <span data-ttu-id="41022-191">Correlationid.</span><span class="sxs-lookup"><span data-stu-id="41022-191">CorrelationID.</span></span> <span data-ttu-id="41022-192">Zeigen Sie die Quelle einer der Office-Seiten an, suchen Sie nach dem Korrelations-ID-Wert, und senden Sie ihn an die Unterstützung:</span><span class="sxs-lookup"><span data-stu-id="41022-192">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="41022-193">Rich Clients (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="41022-193">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="41022-194">Charles/Fiddler-Protokolle</span><span class="sxs-lookup"><span data-stu-id="41022-194">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="41022-195">Erstellen von Nummern der Client-App (vorzugsweise als Screenshot aus **Datei/Konto)**</span><span class="sxs-lookup"><span data-stu-id="41022-195">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |

## <a name="related-content"></a><span data-ttu-id="41022-196">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="41022-196">Related content</span></span>

<span data-ttu-id="41022-197">[Bereitstellen von Add-Ins im Admin Center](../manage/manage-deployment-of-add-ins.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="41022-197">[Deploy add-ins in the admin center](../manage/manage-deployment-of-add-ins.md) (article)</span></span>\
<span data-ttu-id="41022-198">[Verwalten von Add-Ins im Admin Center](manage-addins-in-the-admin-center.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="41022-198">[Manage add-ins in the admin center](manage-addins-in-the-admin-center.md) (article)</span></span>\
<span data-ttu-id="41022-199">[Häufig gestellte Fragen](../manage/centralized-deployment-faq.md) zur zentralen Bereitstellung (Artikel)</span><span class="sxs-lookup"><span data-stu-id="41022-199">[Centralized Deployment FAQ](../manage/centralized-deployment-faq.md) (article)</span></span>\
<span data-ttu-id="41022-200">[Aktualisieren Ihrer Microsoft 365 für Geschäftsbenutzer auf den neuesten Office-Client](../setup/upgrade-users-to-latest-office-client.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="41022-200">[Upgrade your Microsoft 365 for business users to the latest Office client](../setup/upgrade-users-to-latest-office-client.md) (article)</span></span>
 