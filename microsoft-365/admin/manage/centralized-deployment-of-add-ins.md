---
title: Ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Ermitteln Sie, ob Ihr Mandant und die Benutzer die Anforderungen erfüllen, damit Sie die zentrale Bereitstellung für die Bereitstellung von Office-Add-Ins verwenden können.
ms.openlocfilehash: 04c5f9090ca788f00f2d17d3af59e8022195e9be
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519365"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="e5d31-103">Ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert</span><span class="sxs-lookup"><span data-stu-id="e5d31-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="e5d31-104">Die zentrale Bereitstellung ist die empfohlene und funktionsreichste Möglichkeit für die meisten Kunden, Office-Add-Ins für Benutzer und Gruppen in Ihrer Organisation bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e5d31-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="e5d31-105">Wenn Sie Administrator sind, ermitteln Sie anhand dieser Anleitung, ob Ihre Organisation und die Benutzer die Anforderungen erfüllen, damit Sie die zentralisierte Bereitstellung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e5d31-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="e5d31-106">Die zentrale Bereitstellung bietet die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="e5d31-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="e5d31-107">Ein globaler Administrator kann ein Add-in direkt einem Benutzer, mehreren Benutzern über eine Gruppe oder allen in der Organisation zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e5d31-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="e5d31-108">Wenn die entsprechende Office-Anwendung gestartet wird, lädt das Add-in automatisch herunter.</span><span class="sxs-lookup"><span data-stu-id="e5d31-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="e5d31-109">Wenn das Add-in Add-in-Befehle unterstützt, wird das Add-in automatisch im Menüband in der Office-Anwendung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5d31-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="e5d31-110">Add-Ins werden nicht mehr für Benutzer angezeigt, wenn der Administrator das Add-in deaktiviert oder löscht oder wenn der Benutzer aus Azure Active Directory oder aus einer Gruppe entfernt wird, der das Add-in zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e5d31-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="e5d31-111">Die zentralisierte Bereitstellung unterstützt drei Windows-, Mac-und Online Office-Apps für Desktopplattformen.</span><span class="sxs-lookup"><span data-stu-id="e5d31-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="e5d31-112">Die zentralisierte Bereitstellung unterstützt auch IOS und Android (nur Outlook Mobile-Add-Ins).</span><span class="sxs-lookup"><span data-stu-id="e5d31-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="e5d31-113">Es kann bis zu 24 Stunden dauern, bis ein Add-in für alle Benutzer für den Client angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e5d31-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="e5d31-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5d31-114">Requirements</span></span>

<span data-ttu-id="e5d31-115">Die zentrale Bereitstellung von Add-ins erfordert, dass die Benutzer Microsoft 365 Enterprise-SKUs verwenden: E3/E5/F3 oder Geschäfts-SKUs: Business Basic, Business Standard, Business Premium (und mit ihrer Organisations-ID bei Office angemeldet sind) und über Exchange Online und Active Exchange Online-Postfächer verfügen.</span><span class="sxs-lookup"><span data-stu-id="e5d31-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="e5d31-116">Ihr Abonnement Verzeichnis muss sich entweder in oder im Verbund mit Azure Active Directory befinden.</span><span class="sxs-lookup"><span data-stu-id="e5d31-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="e5d31-117">Sie können die spezifischen Anforderungen für Office und Exchange unten anzeigen oder die [Kompatibilitätsprüfung für die zentrale Bereitstellung](#centralized-deployment-compatibility-checker)verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5d31-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="e5d31-118">Folgendes wird von der zentralen Bereitstellung nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="e5d31-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="e5d31-119">Add-Ins, die Word, Excel oder PowerPoint in Office 2013 zum Ziel haben</span><span class="sxs-lookup"><span data-stu-id="e5d31-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="e5d31-120">Ein lokaler Verzeichnisdienst</span><span class="sxs-lookup"><span data-stu-id="e5d31-120">An on-premises directory service</span></span>
- <span data-ttu-id="e5d31-121">Add-in-Bereitstellung in einem Exchange-basierten Postfach</span><span class="sxs-lookup"><span data-stu-id="e5d31-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="e5d31-122">Add-In-Bereitstellung in SharePoint</span><span class="sxs-lookup"><span data-stu-id="e5d31-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="e5d31-123">Microsoft Teams-apps</span><span class="sxs-lookup"><span data-stu-id="e5d31-123">Teams apps</span></span>
- <span data-ttu-id="e5d31-124">Bereitstellung von Component Object Model (com) oder Visual Studio Tools für Office (VSTO)-Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="e5d31-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="e5d31-125">Bereitstellungen von Microsoft 365, die keine Exchange Online wie SKUs enthalten: Microsoft 365 apps for Business und Microsoft 365 apps for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e5d31-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="e5d31-126">Office-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5d31-126">Office Requirements</span></span>

- <span data-ttu-id="e5d31-127">Für Word-, Excel-und PowerPoint-Add-Ins müssen die Benutzer eine der folgenden Optionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="e5d31-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="e5d31-128">Auf einem Windows-Gerät Version 1704 oder höher von Microsoft 365 Enterprise-SKUs: E3/E5/F3 oder Business-SKUs: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="e5d31-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="e5d31-129">Auf einem Mac, Version 15,34 oder höher.</span><span class="sxs-lookup"><span data-stu-id="e5d31-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="e5d31-130">Für Outlook müssen die Benutzer eine der folgenden Optionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="e5d31-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="e5d31-131">Version 1701 oder höher von Microsoft 365 Enterprise-SKUs: E3/E5/F3 oder Business-SKUs: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="e5d31-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="e5d31-132">Version 1808 oder höher von Office Professional Plus 2019 oder Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="e5d31-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="e5d31-133">Version 16.0.4494.1000 oder höher von Office Professional Plus 2016 (MSI) oder Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="e5d31-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="e5d31-134">Version 15.0.4937.1000 oder höher von Office Professional Plus 2013 (MSI) oder Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="e5d31-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="e5d31-135">Version 16.0.9318.1000 oder höher von Office 2016 für Mac</span><span class="sxs-lookup"><span data-stu-id="e5d31-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="e5d31-136">Version 2.75.0 oder höher von Outlook Mobile für IOS</span><span class="sxs-lookup"><span data-stu-id="e5d31-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="e5d31-137">Version 2.2.145 oder höher von Outlook Mobile für Android</span><span class="sxs-lookup"><span data-stu-id="e5d31-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="e5d31-138">\* MSI-Versionen von Outlook zeigen Administrator installierte Add-Ins im entsprechenden Outlook-Menüband, nicht im Abschnitt "meine Add-Ins".</span><span class="sxs-lookup"><span data-stu-id="e5d31-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="e5d31-139">Exchange Online Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5d31-139">Exchange Online requirements</span></span>

<span data-ttu-id="e5d31-140">Microsoft Exchange speichert die Add-in-Manifeste im Mandanten Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="e5d31-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="e5d31-141">Der Administrator, der Add-ins bereitstellt, und die Benutzer, die diese Add-ins empfangen, müssen sich in einer Version von Exchange Online befinden, die die OAuth-Authentifizierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e5d31-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="e5d31-p106">Informieren Sie sich beim Exchange-Administrator Ihrer Organisation, um herauszufinden, welche Konfiguration verwendet wird. Die OAuth-Verbindung pro Benutzer kann überprüft werden, indem Sie das PowerShell-Cmdlet [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5d31-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="e5d31-144">Zentrale Bereitstellungs Kompatibilitätsprüfung</span><span class="sxs-lookup"><span data-stu-id="e5d31-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="e5d31-145">Mithilfe der zentralen Bereitstellungs Kompatibilitätsprüfung können Sie überprüfen, ob die Benutzer Ihres Mandanten für die Verwendung der zentralisierten Bereitstellung für Word, Excel und PowerPoint eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="e5d31-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="e5d31-146">Die Kompatibilitätsprüfung ist für die Unterstützung von Outlook nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e5d31-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="e5d31-147">Laden Sie die Kompatibilitätsprüfung [hier](https://aka.ms/officeaddindeploymentorgcompatibilitychecker) herunter.</span><span class="sxs-lookup"><span data-stu-id="e5d31-147">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="e5d31-148">Ausführen der Kompatibilitätsprüfung</span><span class="sxs-lookup"><span data-stu-id="e5d31-148">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="e5d31-149">Starten Sie ein Fenster mit erhöhten PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="e5d31-149">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="e5d31-150">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="e5d31-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="e5d31-151">Führen Sie den Befehl **Invoke-CompatabilityCheck** aus:</span><span class="sxs-lookup"><span data-stu-id="e5d31-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="e5d31-152">Mit diesem Befehl werden Sie zur Eingabe von  *_TenantDomain_* aufgefordert (beispielsweise *TailspinToysIncorporated. onmicrosoft. </span> com*) und  *_TenantAdmin_* -Anmeldeinformationen (verwenden Sie Ihre globalen Administratoranmeldeinformationen), und fordert dann die Zustimmung an.</span><span class="sxs-lookup"><span data-stu-id="e5d31-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="e5d31-153">Je nach Anzahl der Benutzer Ihres Mandanten kann die Prüfung nach Minuten oder Stunden abgeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="e5d31-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="e5d31-154">Sobald die Ausführung des Tools abgeschlossen ist, wird eine Ausgabedatei im CSV-Format (durch Trennzeichen getrenntes Format) erzeugt.</span><span class="sxs-lookup"><span data-stu-id="e5d31-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="e5d31-155">Die Datei wird standardmäßig in " **system32** " gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e5d31-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="e5d31-156">Die Ausgabedatei enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="e5d31-156">The output file contains the following information:</span></span>
  
- <span data-ttu-id="e5d31-157">Benutzername</span><span class="sxs-lookup"><span data-stu-id="e5d31-157">User Name</span></span>
    
- <span data-ttu-id="e5d31-158">Benutzer-ID (E-Mail-Adresse des Benutzers)</span><span class="sxs-lookup"><span data-stu-id="e5d31-158">User ID (User's email address)</span></span>
    
- <span data-ttu-id="e5d31-159">Zentrale Bereitstellung bereit - Wenn die übrigen Punkte zutreffen</span><span class="sxs-lookup"><span data-stu-id="e5d31-159">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="e5d31-160">Office-Plan – der Plan von Office, für den Sie lizenziert sind</span><span class="sxs-lookup"><span data-stu-id="e5d31-160">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="e5d31-161">Office aktiviert - Wenn Office aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="e5d31-161">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="e5d31-162">Unterstütztes Postfach - Wenn das Postfach für OAuth aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="e5d31-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="e5d31-163">Die mehrstufige Authentifizierung wird bei Verwendung des PowerShell-Moduls für die zentrale Bereitstellung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e5d31-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span>
  
## <a name="user-and-group-assignments"></a><span data-ttu-id="e5d31-164">Benutzer- und Gruppenzuordnungen</span><span class="sxs-lookup"><span data-stu-id="e5d31-164">User and group assignments</span></span>

<span data-ttu-id="e5d31-165">Das zentralisierte Bereitstellungsfeature unterstützt derzeit die Mehrzahl der von Azure Active Directory unterstützten Gruppen, einschließlich Microsoft 365-Gruppen, Verteilerlisten und Sicherheitsgruppen.</span><span class="sxs-lookup"><span data-stu-id="e5d31-165">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e5d31-166">Nicht für E-Mail aktivierte Sicherheitsgruppen werden derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e5d31-166">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="e5d31-167">Die zentralisierte Bereitstellung unterstützt Zuweisungen für einzelne Benutzer, Gruppen und alle Personen im Mandanten.</span><span class="sxs-lookup"><span data-stu-id="e5d31-167">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="e5d31-168">Die zentrale Bereitstellung unterstützt Benutzer in Gruppen der oberen Ebene oder Gruppen ohne übergeordnete Gruppen, jedoch keine Benutzer in geschachtelten Gruppen oder Gruppen, die über übergeordnete Gruppen verfügen.</span><span class="sxs-lookup"><span data-stu-id="e5d31-168">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="e5d31-p110">Schauen Sie sich das folgende Beispiel an, in dem Sandra, Sofia und die Gruppe "Vertriebsabteilung" einem Add-In zugeordnet werden. Da es sich bei "Vertriebsabteilung Westküste" um eine geschachtelte Gruppe handelt, werden Bert und Fred keinem Add-In zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e5d31-p110">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagramm der Vertriebsabteilung](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="e5d31-172">Herausfinden, ob eine Gruppe geschachelte Gruppen enthält</span><span class="sxs-lookup"><span data-stu-id="e5d31-172">Find out if a group contains nested groups</span></span>

<span data-ttu-id="e5d31-173">Die einfachste Methode, um herauszufinden, ob eine Gruppe geschachtelte Gruppen enthält, besteht darin, in Outlook die Gruppenvisitenkarte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e5d31-173">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="e5d31-174">Wenn Sie den Gruppennamen innerhalb des Felds **an** einer e-Mail eingeben und dann den Gruppennamen beim Auflösen auswählen, wird Ihnen angezeigt, ob Sie Benutzer oder geschachtelte Gruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="e5d31-174">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="e5d31-175">Im nachfolgenden Beispiel werden auf der Registerkarte **Mitglieder** der Outlook-Visitenkarte der Testgruppe keine Benutzer und nur zwei Untergruppen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5d31-175">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Registerkarte "Mitglieder" der Outlook-Visitenkarte](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="e5d31-p112">Sie können die umgekehrte Abfrage durchführen, indem Sie die Gruppe auflösen, um zu sehen, ob sie Mitglied einer anderen Gruppe ist. Im Beispiel unten können Sie auf der Registerkarte **Mitgliedschaft** der Outlook-Visitenkarte sehen, dass Untergruppe 1 ein Mitglied der Testgruppe ist.</span><span class="sxs-lookup"><span data-stu-id="e5d31-p112">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Registerkarte "Mitgliedschaft" der Outlook-Visitenkarte](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="e5d31-p113">Alternativ können Sie die Azure Active Directory Graph-API verwenden, um Abfragen auszuführen, um die Liste der Gruppen innerhalb einer Gruppe zu finden. Weitere Informationen finden Sie unter [Vorgänge mit Gruppen | Graph-API-Referenz](https://go.microsoft.com/fwlink/p/?linkid=846342).</span><span class="sxs-lookup"><span data-stu-id="e5d31-p113">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="e5d31-182">Kontaktaufnahme mit dem Microsoft-Support</span><span class="sxs-lookup"><span data-stu-id="e5d31-182">Contacting Microsoft for support</span></span>

<span data-ttu-id="e5d31-183">Wenn Sie oder Ihre Benutzer Probleme beim Laden des Add-ins bei der Verwendung von Office-Apps für das Internet (Word, Excel, etc.) haben, die zentral bereitgestellt wurden, müssen Sie sich möglicherweise an den Microsoft-Support wenden ([Weitere Informationen](../contact-support-for-business-products.md)).</span><span class="sxs-lookup"><span data-stu-id="e5d31-183">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="e5d31-184">Geben Sie die folgenden Informationen zu Ihrer Microsoft 365-Umgebung im Support Ticket an.</span><span class="sxs-lookup"><span data-stu-id="e5d31-184">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="e5d31-185">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="e5d31-185">**Platform**</span></span>|<span data-ttu-id="e5d31-186">**Debuginformationen**</span><span class="sxs-lookup"><span data-stu-id="e5d31-186">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e5d31-187">Office</span><span class="sxs-lookup"><span data-stu-id="e5d31-187">Office</span></span>  <br/> | <span data-ttu-id="e5d31-188">Charles/Fiddler-Protokolle</span><span class="sxs-lookup"><span data-stu-id="e5d31-188">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="e5d31-189">Mandanten-ID ( [So wird's gemacht](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span><span class="sxs-lookup"><span data-stu-id="e5d31-189">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="e5d31-190">CorrelationId.</span><span class="sxs-lookup"><span data-stu-id="e5d31-190">CorrelationID.</span></span> <span data-ttu-id="e5d31-191">Zeigen Sie die Quelle einer der Office-Seiten an, und suchen Sie nach dem Wert der Korrelations-ID, und senden Sie ihn an Support:</span><span class="sxs-lookup"><span data-stu-id="e5d31-191">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="e5d31-192">Rich Clients (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="e5d31-192">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="e5d31-193">Charles/Fiddler-Protokolle</span><span class="sxs-lookup"><span data-stu-id="e5d31-193">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="e5d31-194">Erstellen von Nummern der Client-app (vorzugsweise als Screenshot aus **Datei/Konto**)</span><span class="sxs-lookup"><span data-stu-id="e5d31-194">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   
