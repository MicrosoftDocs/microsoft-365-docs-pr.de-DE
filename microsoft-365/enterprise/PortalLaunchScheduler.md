---
title: Starten Ihres Portals mithilfe des Portal-Start Planungsmoduls
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: In diesem Artikel wird beschrieben, wie Sie Ihr Portal mit dem Start Planer des Portals starten können.
ms.openlocfilehash: 7e488caba5e4df47bb3f51f195e093891565d95c
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367201"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="cb7e8-103">Starten Ihres Portals mithilfe des Portal-Start Planungsmoduls</span><span class="sxs-lookup"><span data-stu-id="cb7e8-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="cb7e8-104">Bei einem Portal handelt es sich um eine SharePoint-Website in Ihrem Intranet mit einer großen Anzahl von Websitebenutzern, die Inhalte auf der Website nutzen.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="cb7e8-105">Das Starten Ihres Portals in Wellen ist ein wichtiger Bestandteil, um sicherzustellen, dass Benutzer über eine reibungslose und leistungsfähige Erfahrung beim Zugriff auf ein neues SharePoint Online Portal verfügen.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="cb7e8-106">Das Starten in Waves ist eine wichtige Möglichkeit zum Rollout Ihres Portals, wie im Abschnitt [Planen des Rollout Plans für die Portal Einführung in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> <span data-ttu-id="cb7e8-107">Der Start Planer des Portals soll Ihnen dabei helfen, einen Wave/Phasen-Roll-Out-Ansatz zu verfolgen, indem Sie die Umleitungen für das neue Portal verwalten.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="cb7e8-108">Während jeder Wellen Phase können Sie Benutzer Feedback erfassen und die Leistung während der einzelnen Bereitstellungsphasen überwachen.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="cb7e8-109">Dies hat den Vorteil, dass Sie das Portal langsam einführen und Ihnen die Möglichkeit geben, Probleme zu unterbrechen und zu beheben, bevor Sie mit der nächsten Welle fortfahren, und letztendlich eine positive Benutzererfahrung sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="cb7e8-110">Es gibt zwei Arten von Umleitungen:</span><span class="sxs-lookup"><span data-stu-id="cb7e8-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="cb7e8-111">Bidirektional: Einführung eines neuen modernen SharePoint Online-Portals zum Ersetzen eines vorhandenen SharePoint-Klassikers oder modernen Portals</span><span class="sxs-lookup"><span data-stu-id="cb7e8-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="cb7e8-112">temporäre seitenumleitung: Einführung eines neuen modernen SharePoint Online-Portals ohne vorhandenes SharePoint-Portal</span><span class="sxs-lookup"><span data-stu-id="cb7e8-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="cb7e8-113">Der Start Planer des Portals steht nur für moderne SharePoint Online-Portale, also für Kommunikationswebsites und moderne Teamwebsites zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-113">The portal launch scheduler is only available to launch modern SharePoint Online portals, i.e. communication sites and modern team sites.</span></span> <span data-ttu-id="cb7e8-114">Starts müssen mindestens 7 Tage im Voraus geplant werden.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="cb7e8-115">Die Anzahl der erforderlichen Wellen wird durch die erwartete Anzahl von Benutzern bestimmt.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="cb7e8-116">Vor dem Planen eines Portal Starts muss das [Tool Seite Diagnostics für SharePoint](https://aka.ms/perftool) ausgeführt werden, um zu überprüfen, ob die Homepage im Portal fehlerfrei ist.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="cb7e8-117">Am Ende des Starts des Portals können alle Benutzer mit Berechtigungen für die Website auf die neue Website zugreifen.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="cb7e8-118">Weitere Informationen zum Starten eines erfolgreichen Portals finden Sie Untergrund Legende Prinzipien, Vorgehensweisen und Empfehlungen, die unter [Creating, Launching and maintaine a healthy Portal](https://docs.microsoft.com/sharepoint/portal-health)beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](https://docs.microsoft.com/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="cb7e8-119">Dieses Feature ist nicht verfügbar für Office 365 Deutschland, Office 365 betrieben von 21Vianet (China) oder Microsoft 365 US Government Plans.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="cb7e8-120">Einrichten von apps und Herstellen einer Verbindung mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb7e8-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="cb7e8-121">[Neueste Microsoft Office SharePoint Online-Verwaltungsshell herunterladen](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="cb7e8-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="cb7e8-p104">Wenn Sie eine frühere Version der Microsoft Office SharePoint Online-Verwaltungsshell installiert haben, gehen Sie zu Programme hinzufügen oder entfernen und deinstallieren Sie "SharePoint Online-Verwaltungsshell".</span><span class="sxs-lookup"><span data-stu-id="cb7e8-p104">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="cb7e8-123">Wählen Sie auf der Seite Download Center Ihre Sprache aus, und klicken Sie dann auf „Herunterladen“.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="cb7e8-124">Wählen Sie eine x64- oder eine x86-MSI-Datei aus.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="cb7e8-125">Laden Sie die x64-Datei herunter, wenn Sie mit der 64-Bit-Version von Windows arbeiten, oder die x86-Datei, wenn Sie mit der 32-Bit-Version arbeiten.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="cb7e8-126">Wenn Sie sich nicht sicher sind, ziehen Sie [Welche Version des Windows-Betriebssystems verwende ich?](https://support.microsoft.com/help/13443/windows-which-operating-system) zurate.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="cb7e8-127">Nachdem die Sie die Datei heruntergeladen haben, führen Sie die Datei aus und folgen Sie den Schritten im Setup-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="cb7e8-128">Stellen Sie eine Verbindung zu Microsoft Office SharePoint Online als [Globaler Admin oder Microsoft Office SharePoint Online-Admin](/sharepoint/sharepoint-admin-role) in Microsoft 365 her.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="cb7e8-129">Eine Anleitung dazu finden Sie unter [Erste Schritte mit der Microsoft Office SharePoint Online-Verwaltungsshell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="cb7e8-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="cb7e8-130">Anzeigen aller vorhandenen Portal-Start-Setups</span><span class="sxs-lookup"><span data-stu-id="cb7e8-130">View any existing portal launch setups</span></span>

<span data-ttu-id="cb7e8-131">So prüfen Sie, ob es vorhandene Portal Startkonfigurationen gibt:</span><span class="sxs-lookup"><span data-stu-id="cb7e8-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="cb7e8-132">Planen eines Portal Starts auf der Website</span><span class="sxs-lookup"><span data-stu-id="cb7e8-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="cb7e8-133">Die Anzahl der erforderlichen Wellen hängt von der erwarteten Startgröße ab.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="cb7e8-134">Weniger als 10.000 Benutzer: 1 Welle</span><span class="sxs-lookup"><span data-stu-id="cb7e8-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="cb7e8-135">10K bis 30K Benutzer: 3 Wellen</span><span class="sxs-lookup"><span data-stu-id="cb7e8-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="cb7e8-136">30K + to 100K users: 5 Waves</span><span class="sxs-lookup"><span data-stu-id="cb7e8-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="cb7e8-137">Mehr als 100K Benutzer: 5 Wellen und wenden Sie sich an Ihr Microsoft-Konto Team</span><span class="sxs-lookup"><span data-stu-id="cb7e8-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="cb7e8-138">Schritte für die bidirektionale Umleitung</span><span class="sxs-lookup"><span data-stu-id="cb7e8-138">Steps for bidirectional redirection</span></span>

<span data-ttu-id="cb7e8-139">Die bidirektionale Umleitung umfasst die Einführung eines neuen modernen SharePoint Online-Portals zum Ersetzen eines vorhandenen SharePoint-Klassikers oder modernen Portals.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="cb7e8-140">Benutzer in aktiven Wellen werden an die neue Website umgeleitet, unabhängig davon, ob Sie zu der alten oder neuen Website navigieren.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="cb7e8-141">Benutzer in einer nicht gestarteten Welle, die versuchen, auf die neue Website zuzugreifen, werden zurück an die alte Website umgeleitet, bis Ihre Wave gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="cb7e8-142">Wir unterstützen nur die Umleitung zwischen der Standardhomepage auf der alten Website und der Standardhomepage auf der neuen Website.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-142">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="cb7e8-143">Wenn Sie Administratoren oder Besitzer haben, die Zugriff auf die alten und neuen Websites benötigen, ohne umgeleitet zu werden, stellen Sie sicher, dass Sie mit dem Parameter aufgelistet werden `WaveOverrideUsers` .</span><span class="sxs-lookup"><span data-stu-id="cb7e8-143">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span> <span data-ttu-id="cb7e8-144">Wenn Sie Administratoren oder Besitzer haben, die Zugriff auf die alten und neuen Websites benötigen, ohne umgeleitet zu werden, stellen Sie sicher, dass Sie mit dem Parameter aufgelistet werden `WaveOverrideUsers` .</span><span class="sxs-lookup"><span data-stu-id="cb7e8-144">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span> <span data-ttu-id="cb7e8-145">Wir unterstützen nur die Umleitung zwischen der Standardhomepage auf der alten Website und der Standardhomepage auf der neuen Website.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-145">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span>

<span data-ttu-id="cb7e8-146">So migrieren Sie Benutzer von einer vorhandenen SharePoint-Website zu einer neuen SharePoint-Website in einer stufenweise:</span><span class="sxs-lookup"><span data-stu-id="cb7e8-146">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="cb7e8-147">Führen Sie den folgenden Befehl aus, um Portal Start Wellen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-147">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="cb7e8-148">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cb7e8-148">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="cb7e8-149">Vollständige Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-149">Complete validation.</span></span> <span data-ttu-id="cb7e8-150">Es kann 5-10 Minuten dauern, bis die Umleitung seine Konfiguration im gesamten Dienst abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-150">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="cb7e8-151">Schritte für die Umleitung zu einer temporären Seite</span><span class="sxs-lookup"><span data-stu-id="cb7e8-151">Steps for redirection to temporary page</span></span>

<span data-ttu-id="cb7e8-152">Die temporäre seitenumleitung sollte verwendet werden, wenn kein vorhandenes SharePoint-Portal vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-152">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="cb7e8-153">Benutzer werden in einer inszenierten Weise zu einem neuen modernen SharePoint Online Portal geleitet.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-153">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="cb7e8-154">Wenn sich ein Benutzer in einer Welle befindet, die noch nicht gestartet wurde, wird er an eine temporäre Seite (eine beliebige URL) umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-154">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="cb7e8-155">Führen Sie den folgenden Befehl aus, um Portal Start Wellen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-155">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="cb7e8-156">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cb7e8-156">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="cb7e8-157">Vollständige Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-157">Complete validation.</span></span> <span data-ttu-id="cb7e8-158">Es kann 5-10 Minuten dauern, bis die Umleitung seine Konfiguration im gesamten Dienst abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-158">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="cb7e8-159">Anhalten oder Neustarten eines Portal Starts auf der Website</span><span class="sxs-lookup"><span data-stu-id="cb7e8-159">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="cb7e8-160">Führen Sie den folgenden Befehl aus, um den laufenden Start des Portals anzuhalten und vorübergehend bevorstehende Wellen Progressionen zu verhindern:</span><span class="sxs-lookup"><span data-stu-id="cb7e8-160">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="cb7e8-161">Überprüfen Sie, dass alle Benutzer an die alte Website umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-161">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="cb7e8-162">Führen Sie den folgenden Befehl aus, um einen angehenden Portal Start neu zu starten:</span><span class="sxs-lookup"><span data-stu-id="cb7e8-162">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="cb7e8-163">Überprüfen Sie, ob die Umleitung jetzt wiederhergestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-163">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="cb7e8-164">Löschen eines Portal Starts auf der Website</span><span class="sxs-lookup"><span data-stu-id="cb7e8-164">Delete a portal launch on the site</span></span>
1. <span data-ttu-id="cb7e8-165">Erstellen Sie eine Portal Start Wave.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-165">Create a Portal launch Wave.</span></span>
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="cb7e8-166">Führen Sie den folgenden Befehl aus, um einen geplanten oder laufenden Portal Start für eine Website zu löschen.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-166">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. <span data-ttu-id="cb7e8-167">Überprüfen Sie, dass keine Umleitung für alle Benutzer erfolgt.</span><span class="sxs-lookup"><span data-stu-id="cb7e8-167">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="cb7e8-168">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb7e8-168">Learn more</span></span>
[<span data-ttu-id="cb7e8-169">Planen des Rollout Plans für den Portal Start in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb7e8-169">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
