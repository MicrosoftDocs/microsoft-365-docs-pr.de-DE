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
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999579"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="88e96-103">Starten Ihres Portals mithilfe des Portal-Start Planungsmoduls</span><span class="sxs-lookup"><span data-stu-id="88e96-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="88e96-104">Sie können Ihr Portal mit dem Start Planer des Portals starten, indem Sie zunächst die Möglichkeit des Mandanten Administrators validieren, ein Waves für ein neues Portal einzurichten.</span><span class="sxs-lookup"><span data-stu-id="88e96-104">You can launch your portal using the Portal Launch Scheduler by first validating the tenant admin's ability to setup a waves for a new portal.</span></span> <span data-ttu-id="88e96-105">Anschließend kann der Administrator eine Umleitung von Anforderungen überprüfen, basierend auf dem vorhanden sein eines Benutzers in den aktiven Wellen.</span><span class="sxs-lookup"><span data-stu-id="88e96-105">Then the admin can validate a redirection of requests, based on the existence of a user in the active waves.</span></span>

<span data-ttu-id="88e96-106">Weitere Informationen zum Starten eines erfolgreichen Portals finden Sie in den Grundsätzen, Vorgehensweisen und Empfehlungen, die im Thema [erstellen, starten und Verwalten eines gesunden Portals](https://go.microsoft.com/fwlink/?linkid=2105838)erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="88e96-106">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in the [Creating, launching and maintaining a healthy portal](https://go.microsoft.com/fwlink/?linkid=2105838).</span></span> 

## <a name="app-setup"></a><span data-ttu-id="88e96-107">App-Setup</span><span class="sxs-lookup"><span data-stu-id="88e96-107">App setup</span></span>
1. <span data-ttu-id="88e96-108">Deinstallieren Sie, wenn ein vorhandener `Microsoft.Online.SharePoint.PowerShell` von Ihrem Computer über die Systemsteuerung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="88e96-108">Uninstall if there an existing `Microsoft.Online.SharePoint.PowerShell` from your machine through the control panel.</span></span>
2. <span data-ttu-id="88e96-109">Im PowerShell `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` -Durchlauf.</span><span class="sxs-lookup"><span data-stu-id="88e96-109">On PowerShell pass `Install-Module -Name Microsoft.Online.SharePoint.PowerShell`.</span></span>

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="88e96-110">Herstellen einer Verbindung mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="88e96-110">Connect to SharePoint Online</span></span>
1. <span data-ttu-id="88e96-111">Öffnen Sie die [SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.</span><span class="sxs-lookup"><span data-stu-id="88e96-111">Open the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.</span></span>
2. <span data-ttu-id="88e96-112">Stellen Sie eine Verbindung mit Ihrem Mandanten als Administrator her.</span><span class="sxs-lookup"><span data-stu-id="88e96-112">Connect to your tenant as an admin.</span></span>
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  <span data-ttu-id="88e96-113">Geben Sie Ihr Kennwort ein, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="88e96-113">Supply your password when prompted.</span></span>

## <a name="command-to-get-an-existing-setup"></a><span data-ttu-id="88e96-114">Befehl zum Abrufen eines vorhandenen Setups</span><span class="sxs-lookup"><span data-stu-id="88e96-114">Command to get an existing setup</span></span>

<span data-ttu-id="88e96-115">So zeigen Sie vorhandene Portal Startkonfigurationen an:</span><span class="sxs-lookup"><span data-stu-id="88e96-115">To view existing portal launch configurations:</span></span>

1. <span data-ttu-id="88e96-116">Übergeben `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` .</span><span class="sxs-lookup"><span data-stu-id="88e96-116">Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite`.</span></span>
2. <span data-ttu-id="88e96-117">Übergeben Sie den zusätzlichen Parameter `-DisplayFormat Raw` , wenn die Wave-Auflistung als RAW-Eingabeformat formatiert angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="88e96-117">Pass the additional parameter `-DisplayFormat Raw` if you wish to see the wave collection formatted as a raw input format.</span></span>

## <a name="commands-for-bi-directional-redirection"></a><span data-ttu-id="88e96-118">Befehle für die bidirektionale Umleitung</span><span class="sxs-lookup"><span data-stu-id="88e96-118">Commands for bi-directional redirection</span></span>

<span data-ttu-id="88e96-119">So migrieren Sie alte Websitebenutzer in einer mehrstufigen Weise zu der neuen Website:</span><span class="sxs-lookup"><span data-stu-id="88e96-119">To migrate old site users to the new site in a staged manner:</span></span>

1. <span data-ttu-id="88e96-120">Erstellen von Portal Start Wellen</span><span class="sxs-lookup"><span data-stu-id="88e96-120">Create Portal launch waves.</span></span>
   - <span data-ttu-id="88e96-121">Dies gilt nur für die Testphase der frühen Version.</span><span class="sxs-lookup"><span data-stu-id="88e96-121">This is only applicable in the early release test phase.</span></span>
   - <span data-ttu-id="88e96-122">Um die Auswirkungen der Änderung sofort zu testen, müssen Sie sicherstellen, dass die erste Welle `LaunchDateUtc` auf das aktuelle Datum festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="88e96-122">To test the impact of the change immediately, make sure the first wave `LaunchDateUtc` is set to the current date.</span></span> <span data-ttu-id="88e96-123">Wenn Sie dieses Flag nicht angeben, erhalten Sie eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="88e96-123">If you do not supply this flag, you get an error message.</span></span> <span data-ttu-id="88e96-124">Dieser Fehler tritt auf, weil Starts in Production mindestens 7 Tage im Voraus geplant werden müssen.</span><span class="sxs-lookup"><span data-stu-id="88e96-124">This error happens because launches in production must be scheduled at least 7 days in advance.</span></span>

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="88e96-125">Vollständige Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="88e96-125">Complete validation.</span></span>
  - <span data-ttu-id="88e96-126">Es kann bis zu 5 Minuten dauern, bis die Umleitung seine Konfiguration über den Dienst abgeschlossen hat, warten Sie also, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="88e96-126">It can take up to 5 minutes for the redirection to complete its configuration across the service, so please wait before continuing.</span></span>
  - <span data-ttu-id="88e96-127">Wenn Sie sich mit dem angegebenen Benutzer anmelden `WaveOverrideUsers` , ändert sich nichts.</span><span class="sxs-lookup"><span data-stu-id="88e96-127">If you login with the user specified as `WaveOverrideUsers`, then nothing changes.</span></span> <span data-ttu-id="88e96-128">Sie sollten auf der Website bleiben, zu der Sie navigiert sind.</span><span class="sxs-lookup"><span data-stu-id="88e96-128">You should be staying at the site you navigated to.</span></span>
  - <span data-ttu-id="88e96-129">Melden Sie sich bei einem Benutzer an, der Teil der *SG1-Viewer* ist.</span><span class="sxs-lookup"><span data-stu-id="88e96-129">Login with a user who is part of *Viewers SG1*.</span></span>
    - <span data-ttu-id="88e96-130">Navigieren Sie zur alten Website, und Sie sollten zur neuen Website umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="88e96-130">Navigate to the old site and you should be redirected to the new site.</span></span>
    - <span data-ttu-id="88e96-131">Navigieren Sie zur neuen Website, und Sie sollten auf der neuen Website bleiben.</span><span class="sxs-lookup"><span data-stu-id="88e96-131">Navigate to the new site and you should be stay on the new site.</span></span>
    - <span data-ttu-id="88e96-132">Melden Sie sich mit dem Benutzer in *SG2* an, und navigieren Sie zum alten Standort, und bleiben Sie auf der alten Website.</span><span class="sxs-lookup"><span data-stu-id="88e96-132">Log with user in *Viewers SG2* and navigate to the old site and stay on the old site.</span></span>
    - <span data-ttu-id="88e96-133">Navigieren Sie zur neuen Website, und Sie sollten an die alte Website umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="88e96-133">Navigate to the new site and you should be redirected to the old site.</span></span>

3. <span data-ttu-id="88e96-134">Unterbrechen Sie den Portal Start.</span><span class="sxs-lookup"><span data-stu-id="88e96-134">Pause Portal launch.</span></span>
  - <span data-ttu-id="88e96-135">Wenn Sie die Start Wellen anhalten müssen, können Sie Sie für "x" Anzahl der Tage anhalten.</span><span class="sxs-lookup"><span data-stu-id="88e96-135">If you need to pause the launch waves, you can pause them for "x" number of days.</span></span> <span data-ttu-id="88e96-136">Wenn `Status` Sie das Flag auf Pause festlegen, werden alle bevorstehenden Wellen Progressionen verhindert.</span><span class="sxs-lookup"><span data-stu-id="88e96-136">Setting the `Status` flag to pause prevents all upcoming wave progressions.</span></span> 
  - <span data-ttu-id="88e96-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="88e96-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="88e96-138">Dadurch wird überprüft, ob alle Benutzer an die alte Website umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="88e96-138">This validates that all users are redirected to the old site.</span></span>

4. <span data-ttu-id="88e96-139">Starten Sie den Start Verlauf des Portals neu.</span><span class="sxs-lookup"><span data-stu-id="88e96-139">Restart the portal launch progression.</span></span> 
  - <span data-ttu-id="88e96-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="88e96-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="88e96-141">Überprüfen Sie, ob die Umleitung jetzt wiederhergestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="88e96-141">Validate that the redirection is now restored.</span></span>

5. <span data-ttu-id="88e96-142">Löschen Sie ein Portal-Start Setup.</span><span class="sxs-lookup"><span data-stu-id="88e96-142">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="88e96-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="88e96-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="88e96-144">Überprüfen Sie, dass keine Umleitung für alle Benutzer erfolgt.</span><span class="sxs-lookup"><span data-stu-id="88e96-144">Validate that no redirection happens for all users.</span></span>

## <a name="commands-for-redirection-to-temporary-page"></a><span data-ttu-id="88e96-145">Befehle für die Umleitung zu einer temporären Seite</span><span class="sxs-lookup"><span data-stu-id="88e96-145">Commands for redirection to temporary page</span></span>

<span data-ttu-id="88e96-146">Führen Sie die folgenden Schritte aus, wenn Sie nicht über eine frühere Website verfügen und Benutzer nicht auf der neuen Portalseite landen möchten.</span><span class="sxs-lookup"><span data-stu-id="88e96-146">Follow these steps if you have no previous site and you want to omit users not in the wave from landing on the new portal page.</span></span>

<span data-ttu-id="88e96-147">So erstellen Sie eine temporäre Seite auf einer der Websites:</span><span class="sxs-lookup"><span data-stu-id="88e96-147">To create a temporary page in any of the sites:</span></span>

1. <span data-ttu-id="88e96-148">Erstellen Sie eine Portal Start Wave.</span><span class="sxs-lookup"><span data-stu-id="88e96-148">Create a Portal launch Wave.</span></span>
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="88e96-149">Vollständige Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="88e96-149">Complete validation.</span></span>

  - <span data-ttu-id="88e96-150">Warten Sie fünf Minuten, bevor Sie fortfahren, da die Ausführung der Aktion bis zu fünf Minuten dauern kann.</span><span class="sxs-lookup"><span data-stu-id="88e96-150">Wait five minutes before continuing, as the action can take up to five minutes to complete.</span></span>
  - <span data-ttu-id="88e96-151">Melden Sie sich mit dem Benutzer an, der Teil der *Viewer-SG1* ist, und:</span><span class="sxs-lookup"><span data-stu-id="88e96-151">Log with the user who is part of *Viewers SG1* and:</span></span>
     - <span data-ttu-id="88e96-152">Navigieren Sie zur neuen Website, und Sie sollten auf der neuen Website bleiben.</span><span class="sxs-lookup"><span data-stu-id="88e96-152">Navigate to the new site, and you should be stay on the new site.</span></span>
     - <span data-ttu-id="88e96-153">Navigieren Sie zur Seite Temp, und Sie sollten auf der Seite Temp bleiben.</span><span class="sxs-lookup"><span data-stu-id="88e96-153">Navigate to the temp page, and you should be stay on the temp page.</span></span>
  - <span data-ttu-id="88e96-154">Melden Sie sich mit dem Benutzer an, der Teil der *Viewer-SG2* ist, und:</span><span class="sxs-lookup"><span data-stu-id="88e96-154">Log with the user who is part of *Viewers SG2* and:</span></span>
     - <span data-ttu-id="88e96-155">Navigieren Sie zur neuen Website, und Sie sollten zur Seite Temp umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="88e96-155">Navigate to the new site, and you should be redirected to the temp page.</span></span>
     - <span data-ttu-id="88e96-156">Navigieren Sie zur Seite Temp, und Sie sollten auf der Seite Temp bleiben.</span><span class="sxs-lookup"><span data-stu-id="88e96-156">Navigate to the temp page, and you should stay on the temp page.</span></span>

3. <span data-ttu-id="88e96-157">Löschen Sie ein Portal-Start Setup.</span><span class="sxs-lookup"><span data-stu-id="88e96-157">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="88e96-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="88e96-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="88e96-159">Überprüfen Sie, dass keine Umleitung für alle Benutzer erfolgt.</span><span class="sxs-lookup"><span data-stu-id="88e96-159">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="88e96-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="88e96-160">Learn more</span></span>
[<span data-ttu-id="88e96-161">Planen des Rollout Plans für den Portal Start in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="88e96-161">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)