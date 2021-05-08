---
title: Starten Des Portals mithilfe des Portalstartplans
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
description: In diesem Artikel wird beschrieben, wie Sie Ihr Portal mit dem Portalstartplaner starten können.
ms.openlocfilehash: 1e62446054f91ff5d2c99520ca65c1681d899ac9
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272056"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a><span data-ttu-id="3728a-103">Starten Des Portals mit dem Startplaner für das SharePoint-Portal</span><span class="sxs-lookup"><span data-stu-id="3728a-103">Launch your portal using the SharePoint Portal launch scheduler</span></span>

<span data-ttu-id="3728a-104">Ein Portal ist eine SharePoint-Kommunikationswebsite in Ihrem Intranet mit hohem Datenverkehr – eine Website, die über mehrere Wochen zwischen 10.000 und über 100.000 Viewern verfügt.</span><span class="sxs-lookup"><span data-stu-id="3728a-104">A portal is a SharePoint communication site on your intranet that is high-traffic – a site that has anywhere from 10,000 to over 100,000 viewers over the course of several weeks.</span></span> <span data-ttu-id="3728a-105">Verwenden Sie den Portalstartplaner, um Ihr Portal zu starten, um sicherzustellen, dass Benutzer beim Zugriff auf Ihr neues SharePoint-Portal eine reibungslose Anzeige haben.</span><span class="sxs-lookup"><span data-stu-id="3728a-105">Use the Portal launch scheduler to launch your portal to ensure users have a smooth viewing experience when accessing your new SharePoint portal.</span></span>
<br>
<br>
<span data-ttu-id="3728a-106">Der Startplaner des Portals soll Ihnen dabei helfen, einen schrittweisen Roll-out-Ansatz zu verfolgen, indem Sie Viewer in Wellen stapeln und die URL-Umleitungen für das neue Portal verwalten.</span><span class="sxs-lookup"><span data-stu-id="3728a-106">The Portal launch scheduler is designed to help you follow a phased roll-out approach by batching viewers in waves and managing the URL redirects for the new portal.</span></span> <span data-ttu-id="3728a-107">Während des Start jeder Welle können Sie Benutzerfeedback sammeln, die Portalleistung überwachen und den Start anhalten, um Probleme zu beheben, bevor Sie mit der nächsten Welle fortfahren.</span><span class="sxs-lookup"><span data-stu-id="3728a-107">During the launch of each wave, you can gather user feedback, monitor portal performance, and pause the launch to resolve issues before proceeding with the next wave.</span></span> <span data-ttu-id="3728a-108">Erfahren Sie mehr über die [Planung eines Portalstarts in SharePoint](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="3728a-108">Learn more about how to [plan a portal launch in SharePoint](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> 

<span data-ttu-id="3728a-109">**Es gibt zwei Arten von Umleitungen:**</span><span class="sxs-lookup"><span data-stu-id="3728a-109">**There are two types of redirections:**</span></span>

- <span data-ttu-id="3728a-110">**Bidirektional:** Starten eines neuen modernen SharePoint-Portals, um ein vorhandenes klassisches oder modernes SharePoint-Portal zu ersetzen</span><span class="sxs-lookup"><span data-stu-id="3728a-110">**Bidirectional**: launch a new modern SharePoint portal to replace an existing SharePoint classic or modern portal</span></span>
- <span data-ttu-id="3728a-111">**Umleitung zu einer temporären Seite:** Starten eines neuen modernen SharePoint-Portals ohne vorhandenes SharePoint-Portal</span><span class="sxs-lookup"><span data-stu-id="3728a-111">**Redirect to a temporary page**: launch a new modern SharePoint portal with no existing SharePoint portal</span></span>

<span data-ttu-id="3728a-112">Websiteberechtigungen müssen im Rahmen des Startstarts getrennt von Wellen eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="3728a-112">Site permissions must be set up separately from waves as part of the launch.</span></span> <span data-ttu-id="3728a-113">Wenn Sie beispielsweise ein organisationsweites Portal freigeben, können Sie Berechtigungen auf "Jeder außer externen Benutzern" festlegen und Ihre Benutzer mithilfe von Sicherheitsgruppen in Wellen trennen.</span><span class="sxs-lookup"><span data-stu-id="3728a-113">For example, if you are releasing an organization-wide portal, you can set permissions to “Everyone except external users,” then separate your users into waves using security groups.</span></span> <span data-ttu-id="3728a-114">Das Hinzufügen einer Sicherheitsgruppe zu einer Welle bietet dieser Sicherheitsgruppe keinen Zugriff auf die Website.</span><span class="sxs-lookup"><span data-stu-id="3728a-114">Adding a security group to a wave does not give that security group access to the site.</span></span> 


> [!NOTE]
> - <span data-ttu-id="3728a-115">Auf dieses Feature kann  ab Mai 2021 im Bereich Einstellungen auf der Homepage der SharePoint-Kommunikationswebsites für Kunden mit gezielter Veröffentlichung zugegriffen werden und wird bis Juli 2021 für alle Kunden verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="3728a-115">This will feature will be accessible from the **Settings** panel on the home page of SharePoint communication sites for Targeted release customers starting in May 2021 and will become available to all customers by July 2021</span></span>
> - <span data-ttu-id="3728a-116">Die PowerShell-Version dieses Tools ist heute verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3728a-116">The PowerShell version of this tool is available today</span></span>
> - <span data-ttu-id="3728a-117">Dieses Feature kann nur auf modernen SharePoint-Kommunikationswebsites verwendet werden</span><span class="sxs-lookup"><span data-stu-id="3728a-117">This feature can only be used on modern SharePoint communication sites</span></span>
> - <span data-ttu-id="3728a-118">Sie müssen über Websitebesitzerberechtigungen für die Website verfügen, um den Start eines Portals anpassen und planen zu können.</span><span class="sxs-lookup"><span data-stu-id="3728a-118">You must have site owner permissions for the site to customize and schedule the launch of a portal</span></span>
> - <span data-ttu-id="3728a-119">Starts müssen mindestens sieben Tage im Voraus geplant sein, und jede Welle kann ein bis sieben Tage dauern.</span><span class="sxs-lookup"><span data-stu-id="3728a-119">Launches must be scheduled at least seven days in advance and each wave can last one to seven days</span></span>
> - <span data-ttu-id="3728a-120">Die Anzahl der erforderlichen Wellen wird automatisch von der erwarteten Anzahl von Benutzern bestimmt.</span><span class="sxs-lookup"><span data-stu-id="3728a-120">The number of waves required is automatically determined by the expected number of users</span></span> 
> - <span data-ttu-id="3728a-121">Vor dem Planen eines Portalstarts muss das Tool Seitendiagnose für [SharePoint](https://aka.ms/perftool) ausgeführt werden, um sicherzustellen, dass die Homepage der Website fehlerfrei ist.</span><span class="sxs-lookup"><span data-stu-id="3728a-121">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page of the site is healthy</span></span>
> - <span data-ttu-id="3728a-122">Am Ende des Startstarts können alle Benutzer mit Berechtigungen für die Website auf die neue Website zugreifen.</span><span class="sxs-lookup"><span data-stu-id="3728a-122">At the end of the launch, all users with permissions to the site will be able to access the new site</span></span>
> - <span data-ttu-id="3728a-123">Wenn Ihre Organisation ["Viva Connections"](https://docs.microsoft.com/SharePoint/viva-connections)verwendet, können Benutzer das Symbol Ihrer Organisation in der Microsoft Teams-App-Leiste sehen. Wenn das Symbol ausgewählt ist, können Benutzer jedoch erst auf das Portal zugreifen, nachdem ihre Welle gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="3728a-123">If your organization is using [Viva Connections](https://docs.microsoft.com/SharePoint/viva-connections), users may see your organization's icon in the Microsoft Teams app bar, however when the icon is selected users will not be able to access the portal until their wave has launched</span></span>
> - <span data-ttu-id="3728a-124">Dieses Feature ist nicht verfügbar für Office 365 Deutschland, Office 365 betrieben von 21Vianet (China) oder Microsoft 365 US Government-Pläne</span><span class="sxs-lookup"><span data-stu-id="3728a-124">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans</span></span>

### <a name="understand-the-differences-between-portal-launch-scheduler-options"></a><span data-ttu-id="3728a-125">Verstehen der Unterschiede zwischen den Optionen für den Startplaner des Portals:</span><span class="sxs-lookup"><span data-stu-id="3728a-125">Understand the differences between Portal launch scheduler options:</span></span>

<span data-ttu-id="3728a-126">Früher konnten Portalstarts nur über SharePoint PowerShell geplant werden.</span><span class="sxs-lookup"><span data-stu-id="3728a-126">Formerly, portal launches could only be scheduled through SharePoint PowerShell.</span></span> <span data-ttu-id="3728a-127">Jetzt stehen Ihnen zwei Optionen zur Verfügung, mit deren Hilfe Sie den Start Ihres Portals planen und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="3728a-127">Now, you have two options to help you schedule and manage your portal's launch.</span></span> <span data-ttu-id="3728a-128">Erfahren Sie mehr über die wichtigsten Unterschiede zwischen beiden Tools:</span><span class="sxs-lookup"><span data-stu-id="3728a-128">Learn about the key differences between both tools:</span></span>

<span data-ttu-id="3728a-129">**SharePoint PowerShell-Version:**</span><span class="sxs-lookup"><span data-stu-id="3728a-129">**SharePoint PowerShell version:**</span></span>

- <span data-ttu-id="3728a-130">Administratoranmeldeinformationen sind für die Verwendung von [SharePoint PowerShell erforderlich](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="3728a-130">Admin credentials are required to use [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps)</span></span> 
- <span data-ttu-id="3728a-131">Mindestanforderung einer Welle</span><span class="sxs-lookup"><span data-stu-id="3728a-131">Minimum requirement of one wave</span></span> 
- <span data-ttu-id="3728a-132">Planen der Startzeit basierend auf der Zeitzone für koordinierte Weltzeit (Coordinated Universal Time, KOORDINIERTE Weltzeit)</span><span class="sxs-lookup"><span data-stu-id="3728a-132">Schedule your launch based on Coordinated Universal Time (UTC) time zone</span></span>

<span data-ttu-id="3728a-133">**Produktversion:**</span><span class="sxs-lookup"><span data-stu-id="3728a-133">**In-product version:**</span></span>

- <span data-ttu-id="3728a-134">Anmeldeinformationen des Websitebesitzers sind erforderlich</span><span class="sxs-lookup"><span data-stu-id="3728a-134">Site owner credentials are required</span></span> 
- <span data-ttu-id="3728a-135">Mindestanforderung von zwei Wellen</span><span class="sxs-lookup"><span data-stu-id="3728a-135">Minimum requirement of two waves</span></span>
- <span data-ttu-id="3728a-136">Planen Des Startes basierend auf der lokalen Zeitzone des Portals, wie in den regionalen Einstellungen angegeben</span><span class="sxs-lookup"><span data-stu-id="3728a-136">Schedule your launch based on the portal's local time zone as indicated in regional settings</span></span>



## <a name="get-started-using-the-portal-launch-scheduler"></a><span data-ttu-id="3728a-137">Erste Schritte mit dem Portalstartplaner</span><span class="sxs-lookup"><span data-stu-id="3728a-137">Get started using the Portal launch scheduler</span></span>

1.  <span data-ttu-id="3728a-138">Fügen Sie vor der Verwendung des Portalstartplantools alle Benutzer  [hinzu,](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) die über Websiteberechtigungen als Websitebesitzer, Websitemitglied oder Besucher Zugriff auf diese Website benötigen.</span><span class="sxs-lookup"><span data-stu-id="3728a-138">Before using the Portal launch scheduler tool, [add all users who will need access to this site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) through **Site permissions** as a Site owner, Site member, or Visitor.</span></span>

2.  <span data-ttu-id="3728a-139">Beginnen Sie dann mit der Planung des Portalstarts, indem Sie auf zwei Arten auf den Portalstartplaner zugreifen:</span><span class="sxs-lookup"><span data-stu-id="3728a-139">Then, start scheduling your portal’s launch by accessing the Portal launch scheduler in one of two ways:</span></span>

    <span data-ttu-id="3728a-140">**Option 1**: Bei der ersten Bearbeitung und Veröffentlichung von Änderungen an Ihrer Homepage – oder bis zur Startseite, Version 3.0 – werden Sie aufgefordert, das Tool zum Starten des Portals zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3728a-140">**Option 1**: The first few times you edit and republish changes to your home page - or up until home page version 3.0 - you will be prompted to use the Portal launch scheduler tool.</span></span> <span data-ttu-id="3728a-141">Wählen **Sie Start planen aus,** um mit der Planung voran zu gehen.</span><span class="sxs-lookup"><span data-stu-id="3728a-141">Select **Schedule launch** to move forward with scheduling.</span></span> <span data-ttu-id="3728a-142">Oder wählen **Sie Erneut veröffentlichen aus,** um Ihre Seitenbearbeitungen erneut zu veröffentlichen, ohne den Start zu planen.</span><span class="sxs-lookup"><span data-stu-id="3728a-142">Or select **Republish** to republish your page edits without scheduling the launch.</span></span>
    
    ![Abbildung der Aufforderung zur Verwendung des Portalstartplans beim erneuten Veröffentlichen der Startseite](../media/portal-launch-republish-2.png)
    
    <span data-ttu-id="3728a-144">**Option 2**: Sie können jederzeit zur Startseite der SharePoint-Kommunikationswebsite  navigieren, Einstellungen auswählen und dann den Start der Website planen, um den Start Ihres Portals zu planen. </span><span class="sxs-lookup"><span data-stu-id="3728a-144">**Option 2**: At any time, you can navigate to the SharePoint communication site home page, select **Settings** and then **Schedule site launch** to schedule your portal’s launch.</span></span>
    
    ![Abbildung des Einstellungsbereichs mit hervorgehobener Planung eines Websitestarts](../media/portal-launch-settings-2.png)

3.  <span data-ttu-id="3728a-146">Bestätigen Sie als Nächstes die Integritätsnote des Portals, und verbessern Sie das Portal bei Bedarf mit dem Tool Seitendiagnose [für SharePoint,](https://aka.ms/perftool) bis Ihr Portal eine **Fehlerfreie Bewertung** erhält.</span><span class="sxs-lookup"><span data-stu-id="3728a-146">Next, confirm the portal’s health score and make improvements to the portal if needed using the [Page Diagnostics for SharePoint](https://aka.ms/perftool) tool until your portal receives a **Healthy** score.</span></span> <span data-ttu-id="3728a-147">Wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="3728a-147">Then, select **Next**.</span></span>

    ![Abbildung des Tools zum Starten des Portals](../media/portal-launch-panel-2.png)
       
    > [!NOTE] 
    > <span data-ttu-id="3728a-149">Der Websitename und die Beschreibung können nicht über den Portalstartplaner  bearbeitet werden, sondern können geändert werden, indem Sie Einstellungen und dann Websiteinformationen auf der Startseite auswählen. </span><span class="sxs-lookup"><span data-stu-id="3728a-149">The site name and description can’t be edited from the Portal launch scheduler and instead can be changed by selecting **Settings** and then **Site information** from the home page.</span></span>
 
4.  <span data-ttu-id="3728a-150">Wählen Sie **in der Dropdownliste die Anzahl** der erwarteten Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="3728a-150">Select the **Number of expected users** from the drop-down.</span></span> <span data-ttu-id="3728a-151">Diese Abbildung stellt die Anzahl der Benutzer dar, die wahrscheinlich Zugriff auf die Website benötigen.</span><span class="sxs-lookup"><span data-stu-id="3728a-151">This figure represents the number of users who will most likely need access to the site.</span></span> <span data-ttu-id="3728a-152">Der Startplaner des Portals bestimmt automatisch die ideale Anzahl von Wellen, je nach den erwarteten Benutzern wie diesem:</span><span class="sxs-lookup"><span data-stu-id="3728a-152">The Portal launch scheduler will automatically determine the ideal number of waves depending on the expected users like this:</span></span>
    
    - <span data-ttu-id="3728a-153">Weniger als 10.000 Benutzer: Zwei Wellen</span><span class="sxs-lookup"><span data-stu-id="3728a-153">Less than 10k users: Two waves</span></span>
    - <span data-ttu-id="3728a-154">10-30-k-Benutzer: Drei Wellen</span><span class="sxs-lookup"><span data-stu-id="3728a-154">10k to 30k users: Three waves</span></span> 
    - <span data-ttu-id="3728a-155">30k+ bis 100k-Benutzer: Fünf Wellen</span><span class="sxs-lookup"><span data-stu-id="3728a-155">30k+ to 100k users: Five waves</span></span>
    - <span data-ttu-id="3728a-156">Mehr als 100.000 Benutzer: Fünf Wellen, und wenden Sie sich an Ihr Microsoft-Kontoteam</span><span class="sxs-lookup"><span data-stu-id="3728a-156">More than 100k users: Five waves and contact your Microsoft account team</span></span>

5.  <span data-ttu-id="3728a-157">Bestimmen Sie dann den typ **der erforderlichen Umleitung:**</span><span class="sxs-lookup"><span data-stu-id="3728a-157">Then, determine the **Type of redirect** needed:</span></span>

    <span data-ttu-id="3728a-158">Option 1: Senden von Benutzern an eine vorhandene **SharePoint-Seite (bidirektional)** – Verwenden Sie diese Option beim Starten eines neuen modernen SharePoint-Portals, um ein vorhandenes SharePoint-Portal zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="3728a-158">**Option 1: Send users to an existing SharePoint page (bidirectional)** – Use this option when launching a new modern SharePoint portal to replace an existing SharePoint portal.</span></span> <span data-ttu-id="3728a-159">Benutzer in aktiven Wellen werden auf die neue Website umgeleitet, unabhängig davon, ob sie zur alten oder zur neuen Website navigieren.</span><span class="sxs-lookup"><span data-stu-id="3728a-159">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="3728a-160">Benutzer in einer nicht gestarteten Welle, die versuchen, auf die neue Website zu zugreifen, werden zurück zur alten Website umgeleitet, bis ihre Welle gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3728a-160">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>
    
    > [!NOTE] 
    > <span data-ttu-id="3728a-161">Bei Verwendung der bidirektionalen Option muss die Person, die den Start anregt, auch über Websitebesitzerberechtigungen für das andere SharePoint-Portal verfügen.</span><span class="sxs-lookup"><span data-stu-id="3728a-161">When using the bidirectional option, the person scheduling the launch must also have site owner permissions to the other SharePoint portal.</span></span>
       
    <span data-ttu-id="3728a-162">**Option 2: Senden** von Benutzern an eine automatisch generierte temporäre Seite (temporäre Seitenumleitung) – Verwenden Sie eine temporäre Seitenumleitung, wenn kein vorhandenes SharePoint-Portal vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3728a-162">**Option 2: Send users to an autogenerated temporary page (temporary page redirection)** – Use a temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="3728a-163">Benutzer werden zu einem neuen modernen SharePoint-Portal weitergeleitet, und wenn sich ein Benutzer in einer Welle befindet, die noch nicht gestartet wurde, werden sie zu einer temporären Seite umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="3728a-163">Users are directed to a new modern SharePoint portal and if a user is in a wave that has not been launched, they will be redirected to a temporary page.</span></span>
    
    <span data-ttu-id="3728a-164">**Option 3: Senden** von Benutzern an eine externe Seite – Geben Sie eine externe URL für eine temporäre Angebotsseite an, bis die Welle des Benutzers gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3728a-164">**Option 3: Send users to an external page** – Provide an external URL to a temporary landing page experience until the user’s wave is launched.</span></span>
    
6.  <span data-ttu-id="3728a-165">Unterlegen Sie Ihre Zielgruppe in Wellen.</span><span class="sxs-lookup"><span data-stu-id="3728a-165">Break up your audience into waves.</span></span> <span data-ttu-id="3728a-166">Add up to 20 security groups per wave.</span><span class="sxs-lookup"><span data-stu-id="3728a-166">Add up to 20 security groups per wave.</span></span> <span data-ttu-id="3728a-167">Wellendetails können bis zum Start jeder Welle bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3728a-167">Wave details can be edited up until the launch of each wave.</span></span> <span data-ttu-id="3728a-168">Jede Welle kann mindestens einen Tag (24 Stunden) und mindestens sieben Tage dauern.</span><span class="sxs-lookup"><span data-stu-id="3728a-168">Each wave can last at minimum one day (24 hours) and at most seven days.</span></span> <span data-ttu-id="3728a-169">Dies ermöglicht SharePoint und Ihrer technischen Umgebung die Möglichkeit, sich auf die große Anzahl von Websitebenutzern zu gewöhnen und zu skalieren.</span><span class="sxs-lookup"><span data-stu-id="3728a-169">This allows SharePoint and your technical environment an opportunity to acclimate and scale to the large volume of site users.</span></span> <span data-ttu-id="3728a-170">Beim Planen eines Startes über die Benutzeroberfläche basiert die Zeitzone auf den regionalen Einstellungen der Website.</span><span class="sxs-lookup"><span data-stu-id="3728a-170">When scheduling a launch through the UI, the time zone is based on the site’s regional settings.</span></span> 

    >[!NOTE] 
    > - <span data-ttu-id="3728a-171">Der Startplaner des Portals wird automatisch auf mindestens 2 Wellen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3728a-171">The Portal launch scheduler will automatically default to a minimum of 2 waves.</span></span> <span data-ttu-id="3728a-172">Die PowerShell-Version dieses Tools ermöglicht jedoch eine Welle.</span><span class="sxs-lookup"><span data-stu-id="3728a-172">However, the PowerShell version of this tool will allow for 1 wave.</span></span>
    >  - <span data-ttu-id="3728a-173">Microsoft 365-Gruppen werden von dieser Version des Portalstartplans nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3728a-173">Microsoft 365 groups are not supported by this version of the Portal launch scheduler.</span></span>

7. <span data-ttu-id="3728a-174">Bestimmen Sie, wer die Website sofort anzeigen muss, und geben Sie ihre Informationen in das Feld Benutzer ein, **die von Wellen ausgenommen** sind.</span><span class="sxs-lookup"><span data-stu-id="3728a-174">Determine who needs to view the site right away and enter their information into the **Users exempt from waves** field.</span></span> <span data-ttu-id="3728a-175">Diese Benutzer sind von Wellen ausgeschlossen und werden nicht vor, während oder nach dem Start umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="3728a-175">These users are excluded from waves and will not be redirected before, during, or after the launch.</span></span>

8.  <span data-ttu-id="3728a-176">Bestätigen Sie die Details zum Starten des Portals, und wählen Sie **Zeitplan aus.**</span><span class="sxs-lookup"><span data-stu-id="3728a-176">Confirm portal launch details and select **Schedule**.</span></span> <span data-ttu-id="3728a-177">Nachdem der Start geplant wurde, müssen alle Änderungen an der Startseite des SharePoint-Portals ein fehlerfreies Diagnoseergebnis erhalten, bevor der Portalstart fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="3728a-177">Once the launch has been scheduled, any changes to the SharePoint portal home page will need to receive a healthy diagnostic result before the portal launch will resume.</span></span>


## <a name="make-changes-to-a-scheduled-portal-launch"></a><span data-ttu-id="3728a-178">Vornehmen von Änderungen an einem geplanten Portalstart</span><span class="sxs-lookup"><span data-stu-id="3728a-178">Make changes to a scheduled portal launch</span></span>

<span data-ttu-id="3728a-179">Startdetails können für jede Welle bis zum Startdatum der Welle bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3728a-179">Launch details can be edited for each wave up until the date of the wave’s launch.</span></span> 

1.  <span data-ttu-id="3728a-180">Navigieren Sie zum Bearbeiten von Portalstartdetails zu **Einstellungen,** und wählen Sie **Websitestart planen aus.**</span><span class="sxs-lookup"><span data-stu-id="3728a-180">To edit portal launch details, navigate to **Settings** and select **Schedule site launch**.</span></span>
2.  <span data-ttu-id="3728a-181">Wählen Sie dann **Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="3728a-181">Then, select **Edit**.</span></span>
3.  <span data-ttu-id="3728a-182">Wenn Sie die Bearbeitungen abgeschlossen haben, wählen Sie **Aktualisieren aus.**</span><span class="sxs-lookup"><span data-stu-id="3728a-182">When you are finished making your edits, select **Update**.</span></span>


## <a name="delete-a-scheduled-portal-launch"></a><span data-ttu-id="3728a-183">Löschen eines geplanten Portalstarts</span><span class="sxs-lookup"><span data-stu-id="3728a-183">Delete a scheduled portal launch</span></span>

<span data-ttu-id="3728a-184">Mit dem Portalstartplanertool geplante Starts können jederzeit abgebrochen oder gelöscht werden, auch wenn bereits einige Wellen gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="3728a-184">Launches scheduled using the Portal launch scheduler tool can be canceled, or deleted, at any time even if some waves have already been launched.</span></span>

1.  <span data-ttu-id="3728a-185">Navigieren Sie zum Abbrechen des Portalstarts zu **Einstellungen** und **Planen des Websitestarts.**</span><span class="sxs-lookup"><span data-stu-id="3728a-185">To cancel your portal’s launch, navigate to **Settings** and **Schedule site launch**.</span></span>

2.  <span data-ttu-id="3728a-186">Wählen Sie dann **Löschen** aus, und wählen Sie dann, wenn die folgende Nachricht angezeigt **wird, erneut Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="3728a-186">Then, select **Delete** and then when you see the message below select **Delete** again.</span></span>

    ![Abbildung des Tools zum Starten des Portals](../media/portal-launch-delete-2.png)


## <a name="use-the-powershell-portal-launch-scheduler"></a><span data-ttu-id="3728a-188">Verwenden des Startzeitplans für das PowerShell-Portal</span><span class="sxs-lookup"><span data-stu-id="3728a-188">Use the PowerShell Portal launch scheduler</span></span>

<span data-ttu-id="3728a-189">Das SharePoint Portal-Startplanertool war ursprünglich nur über [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) verfügbar und wird weiterhin über PowerShell für Kunden unterstützt, die diese Methode bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="3728a-189">The SharePoint Portal launch scheduler tool was originally only available via [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) and will continue to be supported through PowerShell for customers who prefer this method.</span></span> <span data-ttu-id="3728a-190">Die gleichen Hinweise am Anfang dieses Artikels gelten für beide Versionen des Portalstartplans.</span><span class="sxs-lookup"><span data-stu-id="3728a-190">The same notes at the beginning of this article apply to both versions of the Portal launch scheduler.</span></span> 

>[!NOTE]
> <span data-ttu-id="3728a-191">Sie benötigen Administratorberechtigungen für die Verwendung von SharePoint PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3728a-191">You need administrator permissions to use SharePoint PowerShell.</span></span>
> <span data-ttu-id="3728a-192">Portalstartdetails für in PowerShell erstellte Starts werden angezeigt und können im neuen Tool zum Starten des Portals in SharePoint verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="3728a-192">Portal launch details for launches created in PowerShell will appear and can be managed in the new Portal launch scheduler tool in SharePoint.</span></span>


### <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="3728a-193">Einrichten und Herstellen einer Verbindung mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3728a-193">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="3728a-194">[Neueste Microsoft Office SharePoint Online-Verwaltungsshell herunterladen](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="3728a-194">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="3728a-p116">Wenn Sie eine frühere Version der Microsoft Office SharePoint Online-Verwaltungsshell installiert haben, gehen Sie zu Programme hinzufügen oder entfernen und deinstallieren Sie "SharePoint Online-Verwaltungsshell".</span><span class="sxs-lookup"><span data-stu-id="3728a-p116">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="3728a-196">Wählen Sie auf der Seite Download Center Ihre Sprache aus, und klicken Sie dann auf „Herunterladen“.</span><span class="sxs-lookup"><span data-stu-id="3728a-196">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="3728a-197">Wählen Sie eine x64- oder eine x86-MSI-Datei aus.</span><span class="sxs-lookup"><span data-stu-id="3728a-197">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="3728a-198">Laden Sie die x64-Datei herunter, wenn Sie mit der 64-Bit-Version von Windows arbeiten, oder die x86-Datei, wenn Sie mit der 32-Bit-Version arbeiten.</span><span class="sxs-lookup"><span data-stu-id="3728a-198">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="3728a-199">Wenn Sie sich nicht sicher sind, ziehen Sie [Welche Version des Windows-Betriebssystems verwende ich?](https://support.microsoft.com/help/13443/windows-which-operating-system) zurate.</span><span class="sxs-lookup"><span data-stu-id="3728a-199">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="3728a-200">Nachdem die Sie die Datei heruntergeladen haben, führen Sie die Datei aus und folgen Sie den Schritten im Setup-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="3728a-200">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="3728a-201">Stellen Sie eine Verbindung zu Microsoft Office SharePoint Online als [Globaler Admin oder Microsoft Office SharePoint Online-Admin](/sharepoint/sharepoint-admin-role) in Microsoft 365 her.</span><span class="sxs-lookup"><span data-stu-id="3728a-201">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="3728a-202">Eine Anleitung dazu finden Sie unter [Erste Schritte mit der Microsoft Office SharePoint Online-Verwaltungsshell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="3728a-202">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


### <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="3728a-203">Anzeigen vorhandener Portalstarteinrichtung</span><span class="sxs-lookup"><span data-stu-id="3728a-203">View any existing portal launch setups</span></span>

<span data-ttu-id="3728a-204">So sehen Sie, ob vorhandene Portalstartkonfigurationen vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="3728a-204">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="3728a-205">Planen eines Portalstarts auf der Website</span><span class="sxs-lookup"><span data-stu-id="3728a-205">Schedule a portal launch on the site</span></span>

<span data-ttu-id="3728a-206">Die Anzahl der erforderlichen Wellen hängt von der erwarteten Startgröße ab.</span><span class="sxs-lookup"><span data-stu-id="3728a-206">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="3728a-207">Weniger als 10.000 Benutzer: Eine Welle</span><span class="sxs-lookup"><span data-stu-id="3728a-207">Less than 10k users: One wave</span></span>
- <span data-ttu-id="3728a-208">10-30-k-Benutzer: Drei Wellen</span><span class="sxs-lookup"><span data-stu-id="3728a-208">10k to 30k users: Three waves</span></span> 
- <span data-ttu-id="3728a-209">30k+ bis 100k-Benutzer: Fünf Wellen</span><span class="sxs-lookup"><span data-stu-id="3728a-209">30k+ to 100k users: Five waves</span></span>
- <span data-ttu-id="3728a-210">Mehr als 100.000 Benutzer: Fünf Wellen, und wenden Sie sich an Ihr Microsoft-Kontoteam</span><span class="sxs-lookup"><span data-stu-id="3728a-210">More than 100k users: Five waves and contact your Microsoft account team</span></span>

#### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="3728a-211">Schritte für die bidirektionale Umleitung</span><span class="sxs-lookup"><span data-stu-id="3728a-211">Steps for bidirectional redirection</span></span>

<span data-ttu-id="3728a-212">Die bidirektionale Umleitung umfasst das Starten eines neuen modernen SharePoint Online-Portals, um ein vorhandenes klassisches oder modernes SharePoint-Portal zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="3728a-212">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="3728a-213">Benutzer in aktiven Wellen werden auf die neue Website umgeleitet, unabhängig davon, ob sie zur alten oder zur neuen Website navigieren.</span><span class="sxs-lookup"><span data-stu-id="3728a-213">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="3728a-214">Benutzer in einer nicht gestarteten Welle, die versuchen, auf die neue Website zu zugreifen, werden zurück zur alten Website umgeleitet, bis ihre Welle gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3728a-214">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="3728a-215">Wir unterstützen nur die Umleitung zwischen der Standard-Homepage auf der alten Website und der Standard-Homepage auf der neuen Website.</span><span class="sxs-lookup"><span data-stu-id="3728a-215">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="3728a-216">Sollten Sie Administratoren oder Besitzer haben, die Zugriff auf die alten und neuen Websites benötigen, ohne umgeleitet zu werden, stellen Sie sicher, dass sie mit dem Parameter aufgelistet `WaveOverrideUsers` werden.</span><span class="sxs-lookup"><span data-stu-id="3728a-216">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="3728a-217">So migrieren Sie Benutzer von einer vorhandenen SharePoint-Website auf eine neue SharePoint-Website in einer mehrstufigen Weise:</span><span class="sxs-lookup"><span data-stu-id="3728a-217">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="3728a-218">Führen Sie den folgenden Befehl aus, um Portalstartwellen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="3728a-218">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="3728a-219">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3728a-219">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="3728a-220">Vollständige Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="3728a-220">Complete validation.</span></span> <span data-ttu-id="3728a-221">Es kann 5 bis 10 Minuten dauern, bis die Umleitung ihre Konfiguration über den Dienst hinweg abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="3728a-221">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

#### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="3728a-222">Schritte für die Umleitung auf eine temporäre Seite</span><span class="sxs-lookup"><span data-stu-id="3728a-222">Steps for redirection to temporary page</span></span>

<span data-ttu-id="3728a-223">Temporäre Seitenumleitung sollte verwendet werden, wenn kein vorhandenes SharePoint-Portal vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3728a-223">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="3728a-224">Benutzer werden in einer mehrstufigen Weise zu einem neuen modernen SharePoint Online-Portal geleitet.</span><span class="sxs-lookup"><span data-stu-id="3728a-224">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="3728a-225">Wenn sich ein Benutzer in einer Welle befindet, die nicht gestartet wurde, wird er auf eine temporäre Seite (eine beliebige URL) umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="3728a-225">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="3728a-226">Führen Sie den folgenden Befehl aus, um Portalstartwellen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="3728a-226">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="3728a-227">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3728a-227">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="3728a-228">Vollständige Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="3728a-228">Complete validation.</span></span> <span data-ttu-id="3728a-229">Es kann 5 bis 10 Minuten dauern, bis die Umleitung ihre Konfiguration über den Dienst hinweg abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="3728a-229">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="3728a-230">Anhalten oder Neu starten eines Portalstarts auf der Website</span><span class="sxs-lookup"><span data-stu-id="3728a-230">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="3728a-231">Führen Sie den folgenden Befehl aus, um den Start eines Portals anzuhalten und das Auftreten bevorstehender Wellenprogressionen vorübergehend zu verhindern:</span><span class="sxs-lookup"><span data-stu-id="3728a-231">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="3728a-232">Überprüfen Sie, ob alle Benutzer zur alten Website umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="3728a-232">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="3728a-233">Führen Sie den folgenden Befehl aus, um einen angehaltenen Portalstart neu zu starten:</span><span class="sxs-lookup"><span data-stu-id="3728a-233">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="3728a-234">Überprüfen Sie, ob die Umleitung jetzt wiederhergestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3728a-234">Validate that the redirection is now restored.</span></span> 

### <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="3728a-235">Löschen eines Portalstarts auf der Website</span><span class="sxs-lookup"><span data-stu-id="3728a-235">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="3728a-236">Führen Sie den folgenden Befehl aus, um einen geplanten oder in Bearbeitung gelaufenen Portalstart für eine Website zu löschen.</span><span class="sxs-lookup"><span data-stu-id="3728a-236">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="3728a-237">Überprüfen Sie, ob keine Umleitung für alle Benutzer erfolgt.</span><span class="sxs-lookup"><span data-stu-id="3728a-237">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="3728a-238">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3728a-238">Learn more</span></span>

[<span data-ttu-id="3728a-239">Planen des Rolloutplans für den Portalstart in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3728a-239">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)

[<span data-ttu-id="3728a-240">Planen Ihrer Kommunikationswebsite</span><span class="sxs-lookup"><span data-stu-id="3728a-240">Plan your communication site</span></span>](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)