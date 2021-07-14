---
title: Starten Des Portals mithilfe des Portalstartplaners
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
description: In diesem Artikel wird beschrieben, wie Sie Ihr Portal mit dem Portal-Startplaner starten können.
ms.openlocfilehash: dd2b6bdabae5f4d24882912709d6f16a637a9721
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430420"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a><span data-ttu-id="46c7e-103">Starten Des Portals mithilfe des SharePoint Portal-Startplaners</span><span class="sxs-lookup"><span data-stu-id="46c7e-103">Launch your portal using the SharePoint Portal launch scheduler</span></span>

<span data-ttu-id="46c7e-104">Ein Portal ist eine SharePoint Kommunikationswebsite in Ihrem Intranet mit hohem Datenverkehr – eine Website, die über mehrere Wochen zwischen 10.000 und über 100.000 Besucher verfügt.</span><span class="sxs-lookup"><span data-stu-id="46c7e-104">A portal is a SharePoint communication site on your intranet that is high-traffic – a site that has anywhere from 10,000 to over 100,000 viewers over the course of several weeks.</span></span> <span data-ttu-id="46c7e-105">Verwenden Sie den Portal-Startplaner, um Ihr Portal zu starten, um sicherzustellen, dass Benutzer beim Zugriff auf Ihr neues SharePoint Portal eine reibungslose Anzeige haben.</span><span class="sxs-lookup"><span data-stu-id="46c7e-105">Use the Portal launch scheduler to launch your portal to ensure users have a smooth viewing experience when accessing your new SharePoint portal.</span></span>
<br>
<br>
<span data-ttu-id="46c7e-106">Der Portal-Startplaner soll Ihnen dabei helfen, einen schrittweisen Rollout-Ansatz zu verfolgen, indem Sie Viewer in Wellen stapeln und die URL-Umleitungen für das neue Portal verwalten.</span><span class="sxs-lookup"><span data-stu-id="46c7e-106">The Portal launch scheduler is designed to help you follow a phased roll-out approach by batching viewers in waves and managing the URL redirects for the new portal.</span></span> <span data-ttu-id="46c7e-107">Während des Starts jeder Phase können Sie Benutzerfeedback sammeln, die Portalleistung überwachen und den Start anhalten, um Probleme zu beheben, bevor Sie mit der nächsten Welle fortfahren.</span><span class="sxs-lookup"><span data-stu-id="46c7e-107">During the launch of each wave, you can gather user feedback, monitor portal performance, and pause the launch to resolve issues before proceeding with the next wave.</span></span> <span data-ttu-id="46c7e-108">Erfahren Sie mehr darüber, wie Sie [einen Portalstart in SharePoint planen.](/microsoft-365/Enterprise/Planportallaunchroll-out)</span><span class="sxs-lookup"><span data-stu-id="46c7e-108">Learn more about how to [plan a portal launch in SharePoint](/microsoft-365/Enterprise/Planportallaunchroll-out).</span></span>

<span data-ttu-id="46c7e-109">**Es gibt zwei Arten von Umleitungen:**</span><span class="sxs-lookup"><span data-stu-id="46c7e-109">**There are two types of redirections:**</span></span>

- <span data-ttu-id="46c7e-110">**Bidirektional:** Starten eines neuen modernen SharePoint-Portals, um ein vorhandenes SharePoint klassischen oder modernen Portals zu ersetzen</span><span class="sxs-lookup"><span data-stu-id="46c7e-110">**Bidirectional**: launch a new modern SharePoint portal to replace an existing SharePoint classic or modern portal</span></span>
- <span data-ttu-id="46c7e-111">**Umleiten zu einer temporären Seite:** Starten eines neuen modernen SharePoint-Portals ohne vorhandenes SharePoint Portal</span><span class="sxs-lookup"><span data-stu-id="46c7e-111">**Redirect to a temporary page**: launch a new modern SharePoint portal with no existing SharePoint portal</span></span>

<span data-ttu-id="46c7e-112">Websiteberechtigungen müssen im Rahmen des Starts separat von Wellen eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="46c7e-112">Site permissions must be set up separately from waves as part of the launch.</span></span> <span data-ttu-id="46c7e-113">Wenn Sie z. B. ein organisationsweites Portal veröffentlichen, können Sie Berechtigungen auf "Jeder außer externen Benutzern" festlegen und ihre Benutzer dann mithilfe von Sicherheitsgruppen in Wellen aufteilen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-113">For example, if you are releasing an organization-wide portal, you can set permissions to “Everyone except external users,” then separate your users into waves using security groups.</span></span> <span data-ttu-id="46c7e-114">Das Hinzufügen einer Sicherheitsgruppe zu einer Welle gibt dieser Sicherheitsgruppe keinen Zugriff auf die Website.</span><span class="sxs-lookup"><span data-stu-id="46c7e-114">Adding a security group to a wave does not give that security group access to the site.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="46c7e-115">Dieses Feature ist ab Mai 2021 über den **Bereich Einstellungen** auf der Startseite von SharePoint Kommunikationswebsites für Kunden mit gezielter Veröffentlichung verfügbar und wird ab Juli 2021 für alle Kunden verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="46c7e-115">This feature will be accessible from the **Settings** panel on the home page of SharePoint communication sites for Targeted release customers starting in May 2021 and will become available to all customers by July 2021</span></span>
> - <span data-ttu-id="46c7e-116">Die PowerShell-Version dieses Tools ist heute verfügbar.</span><span class="sxs-lookup"><span data-stu-id="46c7e-116">The PowerShell version of this tool is available today</span></span>
> - <span data-ttu-id="46c7e-117">Dieses Feature kann nur auf modernen SharePoint Kommunikationswebsites verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="46c7e-117">This feature can only be used on modern SharePoint communication sites</span></span>
> - <span data-ttu-id="46c7e-118">Sie müssen über Websitebesitzerberechtigungen verfügen, damit die Website den Start eines Portals anpassen und planen kann.</span><span class="sxs-lookup"><span data-stu-id="46c7e-118">You must have site owner permissions for the site to customize and schedule the launch of a portal</span></span>
> - <span data-ttu-id="46c7e-119">Starts müssen mindestens sieben Tage im Voraus geplant sein, und jede Welle kann ein bis sieben Tage dauern.</span><span class="sxs-lookup"><span data-stu-id="46c7e-119">Launches must be scheduled at least seven days in advance and each wave can last one to seven days</span></span>
> - <span data-ttu-id="46c7e-120">Die Anzahl der erforderlichen Wellen wird automatisch durch die erwartete Anzahl von Benutzern bestimmt.</span><span class="sxs-lookup"><span data-stu-id="46c7e-120">The number of waves required is automatically determined by the expected number of users</span></span>
> - <span data-ttu-id="46c7e-121">Vor der Planung eines Portalstarts muss das [Tool "Seitendiagnose für SharePoint"](https://aka.ms/perftool) ausgeführt werden, um zu überprüfen, ob die Startseite der Website fehlerfrei ist.</span><span class="sxs-lookup"><span data-stu-id="46c7e-121">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page of the site is healthy</span></span>
> - <span data-ttu-id="46c7e-122">Am Ende des Starts können alle Benutzer mit Berechtigungen für die Website auf die neue Website zugreifen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-122">At the end of the launch, all users with permissions to the site will be able to access the new site</span></span>
> - <span data-ttu-id="46c7e-123">Wenn Ihre Organisation [Viva Connections](/SharePoint/viva-connections)verwendet, sehen Benutzer möglicherweise das Symbol Ihrer Organisation in der Microsoft Teams App-Leiste. Wenn das Symbol ausgewählt ist, können Benutzer jedoch erst auf das Portal zugreifen, wenn ihre Welle gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="46c7e-123">If your organization is using [Viva Connections](/SharePoint/viva-connections), users may see your organization's icon in the Microsoft Teams app bar, however when the icon is selected users will not be able to access the portal until their wave has launched</span></span>
> - <span data-ttu-id="46c7e-124">Dieses Feature ist nicht für Office 365 Deutschland, Office 365 betrieben von 21Vianet (China) oder Microsoft 365 US Government-Plänen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="46c7e-124">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans</span></span>

## <a name="understand-the-differences-between-portal-launch-scheduler-options"></a><span data-ttu-id="46c7e-125">Grundlegendes zu den Unterschieden zwischen den Optionen des Portal-Startplaners:</span><span class="sxs-lookup"><span data-stu-id="46c7e-125">Understand the differences between Portal launch scheduler options:</span></span>

<span data-ttu-id="46c7e-126">Früher konnten Portalstarts nur über SharePoint PowerShell geplant werden.</span><span class="sxs-lookup"><span data-stu-id="46c7e-126">Formerly, portal launches could only be scheduled through SharePoint PowerShell.</span></span> <span data-ttu-id="46c7e-127">Jetzt stehen Ihnen zwei Optionen zur Verfügung, mit denen Sie den Start Ihres Portals planen und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="46c7e-127">Now, you have two options to help you schedule and manage your portal's launch.</span></span> <span data-ttu-id="46c7e-128">Erfahren Sie mehr über die wichtigsten Unterschiede zwischen beiden Tools:</span><span class="sxs-lookup"><span data-stu-id="46c7e-128">Learn about the key differences between both tools:</span></span>

<span data-ttu-id="46c7e-129">**SharePoint PowerShell-Version:**</span><span class="sxs-lookup"><span data-stu-id="46c7e-129">**SharePoint PowerShell version:**</span></span>

- <span data-ttu-id="46c7e-130">Administratoranmeldeinformationen sind erforderlich, um [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="46c7e-130">Admin credentials are required to use [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)</span></span>
- <span data-ttu-id="46c7e-131">Mindestanforderung einer Welle</span><span class="sxs-lookup"><span data-stu-id="46c7e-131">Minimum requirement of one wave</span></span>
- <span data-ttu-id="46c7e-132">Planen des Starts basierend auf der Utc-Zeitzone (Coordinated Universal Time)</span><span class="sxs-lookup"><span data-stu-id="46c7e-132">Schedule your launch based on Coordinated Universal Time (UTC) time zone</span></span>

<span data-ttu-id="46c7e-133">**Produktinterne Version:**</span><span class="sxs-lookup"><span data-stu-id="46c7e-133">**In-product version:**</span></span>

- <span data-ttu-id="46c7e-134">Anmeldeinformationen des Websitebesitzers sind erforderlich</span><span class="sxs-lookup"><span data-stu-id="46c7e-134">Site owner credentials are required</span></span>
- <span data-ttu-id="46c7e-135">Mindestanforderung von zwei Wellen</span><span class="sxs-lookup"><span data-stu-id="46c7e-135">Minimum requirement of two waves</span></span>
- <span data-ttu-id="46c7e-136">Planen Des Starts basierend auf der lokalen Zeitzone des Portals, wie in den regionalen Einstellungen angegeben</span><span class="sxs-lookup"><span data-stu-id="46c7e-136">Schedule your launch based on the portal's local time zone as indicated in regional settings</span></span>

## <a name="get-started-using-the-portal-launch-scheduler"></a><span data-ttu-id="46c7e-137">Erste Schritte mit dem Portal-Startplaner</span><span class="sxs-lookup"><span data-stu-id="46c7e-137">Get started using the Portal launch scheduler</span></span>

1. <span data-ttu-id="46c7e-138">Bevor Sie das Portal-Startplanungstool verwenden, [fügen Sie alle Benutzer, die Zugriff auf diese Website benötigen,](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) über **Websiteberechtigungen** als Websitebesitzer, Websitemitglied oder Besucher hinzu.</span><span class="sxs-lookup"><span data-stu-id="46c7e-138">Before using the Portal launch scheduler tool, [add all users who will need access to this site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) through **Site permissions** as a Site owner, Site member, or Visitor.</span></span>

2. <span data-ttu-id="46c7e-139">Beginnen Sie dann mit der Planung des Starts Ihres Portals, indem Sie auf zwei Arten auf den Portal-Startplaner zugreifen:</span><span class="sxs-lookup"><span data-stu-id="46c7e-139">Then, start scheduling your portal’s launch by accessing the Portal launch scheduler in one of two ways:</span></span>

   <span data-ttu-id="46c7e-140">**Option 1:** Die ersten Male, in denen Sie Änderungen an Ihrer Startseite bearbeiten und erneut veröffentlichen – oder bis zur Startseite, Version 3.0 – werden Sie aufgefordert, das Portal-Startplanungstool zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="46c7e-140">**Option 1**: The first few times you edit and republish changes to your home page - or up until home page version 3.0 - you will be prompted to use the Portal launch scheduler tool.</span></span> <span data-ttu-id="46c7e-141">Wählen Sie **"Start planen"** aus, um mit der Planung vorwärts zu gehen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-141">Select **Schedule launch** to move forward with scheduling.</span></span> <span data-ttu-id="46c7e-142">Oder wählen Sie **Erneut veröffentlichen,** um Ihre Seitenbearbeitungen erneut zu veröffentlichen, ohne den Start zu planen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-142">Or select **Republish** to republish your page edits without scheduling the launch.</span></span>

   ![Abbildung der Aufforderung zur Verwendung des Portalstartplaners bei der erneuten Veröffentlichung der Startseite](../media/portal-launch-republish-2.png)

   <span data-ttu-id="46c7e-144">**Option 2:** Sie können jederzeit zur Startseite der SharePoint Kommunikationswebsite navigieren, **Einstellungen** auswählen und dann den **Websitestart planen,** um den Start Ihres Portals zu planen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-144">**Option 2**: At any time, you can navigate to the SharePoint communication site home page, select **Settings** and then **Schedule site launch** to schedule your portal’s launch.</span></span>

   ![Abbildung des bereichs Einstellungen mit hervorgehobenem "Planen eines Websitestarts"](../media/portal-launch-settings-2.png)

3. <span data-ttu-id="46c7e-146">Bestätigen Sie als Nächstes die Integritätsbewertung des Portals, und nehmen Sie bei Bedarf Verbesserungen am Portal vor, indem Sie das Tool ["Seitendiagnose für SharePoint"](https://aka.ms/perftool) verwenden, bis Ihr Portal eine **fehlerfreie** Bewertung erhält.</span><span class="sxs-lookup"><span data-stu-id="46c7e-146">Next, confirm the portal’s health score and make improvements to the portal if needed using the [Page Diagnostics for SharePoint](https://aka.ms/perftool) tool until your portal receives a **Healthy** score.</span></span> <span data-ttu-id="46c7e-147">Wählen Sie dann **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="46c7e-147">Then, select **Next**.</span></span>

   ![Abbildung des Portals-Startplanungstools](../media/portal-launch-panel-2.png)

   > [!NOTE]
   > <span data-ttu-id="46c7e-149">Der Websitename und die Beschreibung können nicht über den Portalstartplaner bearbeitet werden und können stattdessen geändert werden, indem **Sie Einstellungen** und dann **Websiteinformationen** auf der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-149">The site name and description can’t be edited from the Portal launch scheduler and instead can be changed by selecting **Settings** and then **Site information** from the home page.</span></span>

4. <span data-ttu-id="46c7e-150">Wählen Sie in der Dropdownliste die **Anzahl der erwarteten Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="46c7e-150">Select the **Number of expected users** from the drop-down.</span></span> <span data-ttu-id="46c7e-151">Diese Abbildung zeigt die Anzahl der Benutzer, die wahrscheinlich Zugriff auf die Website benötigen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-151">This figure represents the number of users who will most likely need access to the site.</span></span> <span data-ttu-id="46c7e-152">Der Portal-Startplaner bestimmt automatisch die ideale Anzahl von Wellen, abhängig von den erwarteten Benutzern wie folgt:</span><span class="sxs-lookup"><span data-stu-id="46c7e-152">The Portal launch scheduler will automatically determine the ideal number of waves depending on the expected users like this:</span></span>

   - <span data-ttu-id="46c7e-153">Weniger als 10.000 Benutzer: Zwei Wellen</span><span class="sxs-lookup"><span data-stu-id="46c7e-153">Less than 10k users: Two waves</span></span>
   - <span data-ttu-id="46c7e-154">10.000 bis 30.000 Benutzer: Drei Wellen</span><span class="sxs-lookup"><span data-stu-id="46c7e-154">10k to 30k users: Three waves</span></span>
   - <span data-ttu-id="46c7e-155">30.000+ bis 100.000 Benutzer: Fünf Wellen</span><span class="sxs-lookup"><span data-stu-id="46c7e-155">30k+ to 100k users: Five waves</span></span>
   - <span data-ttu-id="46c7e-156">Mehr als 100.000 Benutzer: Fünf Phasen, und wenden Sie sich über die schritte im Startportal mit mehr als 100.000 Benutzern an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="46c7e-156">More than 100k users: Five waves and contact your Microsoft via the steps listed in Launch portal with over 100k users section.</span></span>

5. <span data-ttu-id="46c7e-157">Ermitteln Sie dann den typ der benötigten **Umleitung:**</span><span class="sxs-lookup"><span data-stu-id="46c7e-157">Then, determine the **Type of redirect** needed:</span></span>

   <span data-ttu-id="46c7e-158">**Option 1: Senden von Benutzern an eine vorhandene SharePoint Seite (bidirektional)** – Verwenden Sie diese Option beim Starten eines neuen modernen SharePoint-Portals, um ein vorhandenes SharePoint-Portal zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-158">**Option 1: Send users to an existing SharePoint page (bidirectional)** – Use this option when launching a new modern SharePoint portal to replace an existing SharePoint portal.</span></span> <span data-ttu-id="46c7e-159">Benutzer in aktiven Phasen werden zur neuen Website umgeleitet, unabhängig davon, ob sie zur alten oder neuen Website navigieren.</span><span class="sxs-lookup"><span data-stu-id="46c7e-159">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="46c7e-160">Benutzer in einer nicht gestarteten Welle, die versuchen, auf die neue Website zuzugreifen, werden zurück zur alten Website umgeleitet, bis ihre Welle gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="46c7e-160">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>

   > [!NOTE]
   > <span data-ttu-id="46c7e-161">Bei Verwendung der bidirektionalen Option muss die Person, die den Start plant, auch über Berechtigungen des Websitebesitzers für das andere SharePoint Portal verfügen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-161">When using the bidirectional option, the person scheduling the launch must also have site owner permissions to the other SharePoint portal.</span></span>

   <span data-ttu-id="46c7e-162">**Option 2: Senden von Benutzern an eine automatisch generierte temporäre Seite (temporäre Seitenumleitung)** – Verwenden Sie eine temporäre Seitenumleitung, wenn kein vorhandenes SharePoint-Portal vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="46c7e-162">**Option 2: Send users to an autogenerated temporary page (temporary page redirection)** – Use a temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="46c7e-163">Benutzer werden zu einem neuen modernen SharePoint-Portal geleitet, und wenn sich ein Benutzer in einer Welle befindet, die nicht gestartet wurde, werden sie zu einer temporären Seite umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="46c7e-163">Users are directed to a new modern SharePoint portal and if a user is in a wave that has not been launched, they will be redirected to a temporary page.</span></span>

   <span data-ttu-id="46c7e-164">**Option 3: Senden von Benutzern an eine externe Seite** – Geben Sie eine externe URL zu einer temporären Startseite an, bis die Welle des Benutzers gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="46c7e-164">**Option 3: Send users to an external page** – Provide an external URL to a temporary landing page experience until the user’s wave is launched.</span></span>

6. <span data-ttu-id="46c7e-165">Teilen Sie Ihre Zielgruppe in Wellen auf.</span><span class="sxs-lookup"><span data-stu-id="46c7e-165">Break up your audience into waves.</span></span> <span data-ttu-id="46c7e-166">Fügen Sie bis zu 20 Sicherheitsgruppen pro Welle hinzu.</span><span class="sxs-lookup"><span data-stu-id="46c7e-166">Add up to 20 security groups per wave.</span></span> <span data-ttu-id="46c7e-167">Wave-Details können bis zum Start jeder Welle bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="46c7e-167">Wave details can be edited up until the launch of each wave.</span></span> <span data-ttu-id="46c7e-168">Jede Welle kann mindestens einen Tag (24 Stunden) und höchstens sieben Tage dauern.</span><span class="sxs-lookup"><span data-stu-id="46c7e-168">Each wave can last at minimum one day (24 hours) and at most seven days.</span></span> <span data-ttu-id="46c7e-169">Auf diese Weise können SharePoint und Ihre technische Umgebung sich an die große Anzahl von Websitebenutzern gewöhnen und skalieren.</span><span class="sxs-lookup"><span data-stu-id="46c7e-169">This allows SharePoint and your technical environment an opportunity to acclimate and scale to the large volume of site users.</span></span> <span data-ttu-id="46c7e-170">Bei der Planung eines Starts über die Benutzeroberfläche basiert die Zeitzone auf den regionalen Einstellungen der Website.</span><span class="sxs-lookup"><span data-stu-id="46c7e-170">When scheduling a launch through the UI, the time zone is based on the site’s regional settings.</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="46c7e-171">Der Portal-Startplaner wird standardmäßig auf mindestens 2 Wellen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="46c7e-171">The Portal launch scheduler will automatically default to a minimum of 2 waves.</span></span> <span data-ttu-id="46c7e-172">Die PowerShell-Version dieses Tools lässt jedoch eine Welle zu.</span><span class="sxs-lookup"><span data-stu-id="46c7e-172">However, the PowerShell version of this tool will allow for 1 wave.</span></span>
   > - <span data-ttu-id="46c7e-173">Microsoft 365 Gruppen werden von dieser Version des Portalstartplaners nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="46c7e-173">Microsoft 365 groups are not supported by this version of the Portal launch scheduler.</span></span>

7. <span data-ttu-id="46c7e-174">Bestimmen Sie, wer die Website sofort anzeigen muss, und geben Sie ihre Informationen in das **Feld "Benutzer" ein, das vom Wellenfeld ausgenommen ist.**</span><span class="sxs-lookup"><span data-stu-id="46c7e-174">Determine who needs to view the site right away and enter their information into the **Users exempt from waves** field.</span></span> <span data-ttu-id="46c7e-175">Diese Benutzer werden von den Wellen ausgeschlossen und nicht vor, während oder nach dem Start umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="46c7e-175">These users are excluded from waves and will not be redirected before, during, or after the launch.</span></span>

    > [!NOTE]
    > <span data-ttu-id="46c7e-176">Bis zu 50 unterschiedliche Benutzer oder Sicherheitsgruppen können maximal für den gesamten Start verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="46c7e-176">Up to 50 distinct users or security groups max can be used for the entire launch.</span></span> <span data-ttu-id="46c7e-177">Jeder Start ist unabhängig voneinander. Wenn Sie also einen Start auf einem anderen Portal planen, können Sie bis zu 50 Benutzer/Sicherheitsgruppen für diesen Start verwenden.</span><span class="sxs-lookup"><span data-stu-id="46c7e-177">Each launch is independent of each other, so if you schedule a launch on another portal, then you could use up to 50 users/security groups for that launch.</span></span> <span data-ttu-id="46c7e-178">Darüber hinaus können Sie bis zu 20 unterschiedliche Benutzer oder Sicherheitsgruppen pro Welle verwenden.</span><span class="sxs-lookup"><span data-stu-id="46c7e-178">Additionally, you can use up to 20 distinct users or security groups per wave.</span></span> 
    >
    > <span data-ttu-id="46c7e-179">Der Portalstartplaner unterstützt Sicherheitsgruppen und E-Mail-aktivierte Sicherheitsgruppen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-179">The portal launch scheduler supports security groups and mail enabled security groups.</span></span> 

8. <span data-ttu-id="46c7e-180">Bestätigen Sie die Startdetails des Portals, und wählen Sie **"Zeitplan"** aus.</span><span class="sxs-lookup"><span data-stu-id="46c7e-180">Confirm portal launch details and select **Schedule**.</span></span> <span data-ttu-id="46c7e-181">Nachdem der Start geplant wurde, müssen alle Änderungen an der Startseite des SharePoint Portals ein fehlerfreies Diagnoseergebnis erhalten, bevor der Start des Portals fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="46c7e-181">Once the launch has been scheduled, any changes to the SharePoint portal home page will need to receive a healthy diagnostic result before the portal launch will resume.</span></span>

### <a name="launch-a-portal-with-over-100k-users"></a><span data-ttu-id="46c7e-182">Starten eines Portals mit mehr als 100.000 Benutzern</span><span class="sxs-lookup"><span data-stu-id="46c7e-182">Launch a portal with over 100k users</span></span>

<span data-ttu-id="46c7e-183">Wenn Sie planen, ein Portal mit mehr als 100.000 Benutzern zu starten, senden Sie eine Supportanfrage gemäß den unten aufgeführten Schritten.</span><span class="sxs-lookup"><span data-stu-id="46c7e-183">If you are planning to launch a portal with over 100,000 users, submit a support request following the steps listed below.</span></span> <span data-ttu-id="46c7e-184">Achten Sie darauf, alle angeforderten Informationen einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-184">Make sure to include all the requested information.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="46c7e-185">Dieser Prozess sollte nur befolgt werden, wenn Sie die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="46c7e-185">This process should only be followed if you meet the following requirements:</span></span>
> - <span data-ttu-id="46c7e-186">Die Startseite wurde abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-186">The Launch Page has been completed.</span></span>
> - <span data-ttu-id="46c7e-187">[Der Portal-Integritätsleitfaden](https://aka.ms/portalhealth) wurde befolgt.</span><span class="sxs-lookup"><span data-stu-id="46c7e-187">[Portal Health Guidance](https://aka.ms/portalhealth) has been followed.</span></span>
> - <span data-ttu-id="46c7e-188">Das Startdatum liegt innerhalb von 14 Tagen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-188">The Launch date is within 14 days.</span></span>

<span data-ttu-id="46c7e-189">**Führen Sie die folgenden Schritte aus:**</span><span class="sxs-lookup"><span data-stu-id="46c7e-189">**Follow these steps:**</span></span>

1. <span data-ttu-id="46c7e-190">Wechseln Sie zu <https://admin.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="46c7e-190">Go to <https://admin.microsoft.com>.</span></span>
2. <span data-ttu-id="46c7e-191">Stellen Sie sicher, dass Sie die neue Admin Center-Vorschau verwenden</span><span class="sxs-lookup"><span data-stu-id="46c7e-191">Ensure you are using the new admin center preview</span></span>
3. <span data-ttu-id="46c7e-192">Wählen Sie im linken Navigationsbereich **"Support"** und dann **"Neue Serviceanfrage"** aus.</span><span class="sxs-lookup"><span data-stu-id="46c7e-192">On the left navigational pane, select **Support**, and then select **New Service Request**</span></span>

   <span data-ttu-id="46c7e-193">Damit wird der Bereich **Benötigen Sie Hilfe?** auf der rechten Seite des Bildschirms aktiviert.</span><span class="sxs-lookup"><span data-stu-id="46c7e-193">This will activate the **Need Help?** pane on the right-hand side of your screen.</span></span>

4. <span data-ttu-id="46c7e-194">Wenn **Sie Ihr Problem kurz beschreiben** möchten, geben Sie "Start SharePoint Portal mit 100.000 Benutzern" ein.</span><span class="sxs-lookup"><span data-stu-id="46c7e-194">For **Briefly describe your issue**, enter "Launch SharePoint Portal with 100k users"</span></span></br>
5. <span data-ttu-id="46c7e-195">Wählen Sie dann **"Support kontaktieren"** aus.</span><span class="sxs-lookup"><span data-stu-id="46c7e-195">Then, select **Contact Support**</span></span>
6. <span data-ttu-id="46c7e-196">Geben Sie unter **"Beschreibung"** den Eintrag "Start SharePoint Portal mit 100.000 Benutzern" ein.</span><span class="sxs-lookup"><span data-stu-id="46c7e-196">Under **Description**, enter "Launch SharePoint Portal with 100k users"</span></span>
7. <span data-ttu-id="46c7e-197">Füllen Sie die verbleibenden Informationen aus, und wählen Sie dann **"Kontakt"** aus.</span><span class="sxs-lookup"><span data-stu-id="46c7e-197">Fill out the remaining information, and then select **Contact me**</span></span>
8. <span data-ttu-id="46c7e-198">Stellen Sie nach der Erstellung des Tickets sicher, dass Sie dem Supportmitarbeiter folgende Informationen mitteilen:</span><span class="sxs-lookup"><span data-stu-id="46c7e-198">After the ticket has been created, ensure you provide the support agent with the following information:</span></span>
   - <span data-ttu-id="46c7e-199">Portal-URLs</span><span class="sxs-lookup"><span data-stu-id="46c7e-199">Portal URL's</span></span>
   - <span data-ttu-id="46c7e-200">Erwartete Anzahl von Benutzern</span><span class="sxs-lookup"><span data-stu-id="46c7e-200">Number of users expected</span></span>
   - <span data-ttu-id="46c7e-201">Geschätzter Startplan</span><span class="sxs-lookup"><span data-stu-id="46c7e-201">Estimated launch schedule</span></span>

## <a name="make-changes-to-a-scheduled-portal-launch"></a><span data-ttu-id="46c7e-202">Vornehmen von Änderungen an einem geplanten Start eines Portals</span><span class="sxs-lookup"><span data-stu-id="46c7e-202">Make changes to a scheduled portal launch</span></span>

<span data-ttu-id="46c7e-203">Startdetails können für jede Welle bis zum Datum des Starts der Welle bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="46c7e-203">Launch details can be edited for each wave up until the date of the wave’s launch.</span></span>

1. <span data-ttu-id="46c7e-204">Navigieren Sie zum Bearbeiten der Startdetails des Portals zu **Einstellungen,** und wählen Sie **"Websitestart planen"** aus.</span><span class="sxs-lookup"><span data-stu-id="46c7e-204">To edit portal launch details, navigate to **Settings** and select **Schedule site launch**.</span></span>
2. <span data-ttu-id="46c7e-205">Wählen Sie dann **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="46c7e-205">Then, select **Edit**.</span></span>
3. <span data-ttu-id="46c7e-206">Wenn Sie die Bearbeitung abgeschlossen haben, wählen Sie **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="46c7e-206">When you are finished making your edits, select **Update**.</span></span>

## <a name="delete-a-scheduled-portal-launch"></a><span data-ttu-id="46c7e-207">Löschen eines geplanten Portalstarts</span><span class="sxs-lookup"><span data-stu-id="46c7e-207">Delete a scheduled portal launch</span></span>

<span data-ttu-id="46c7e-208">Mit dem Portal-Startplanungstool geplante Starts können jederzeit abgebrochen oder gelöscht werden, auch wenn einige Phasen bereits gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="46c7e-208">Launches scheduled using the Portal launch scheduler tool can be canceled, or deleted, at any time even if some waves have already been launched.</span></span>

1. <span data-ttu-id="46c7e-209">Um den Start Ihres Portals abzubrechen, navigieren Sie zu **Einstellungen** und **planen Sie den Websitestart.**</span><span class="sxs-lookup"><span data-stu-id="46c7e-209">To cancel your portal’s launch, navigate to **Settings** and **Schedule site launch**.</span></span>

2. <span data-ttu-id="46c7e-210">Wählen Sie dann **"Löschen"** und dann, wenn die folgende Meldung angezeigt wird, erneut **"Löschen"** aus.</span><span class="sxs-lookup"><span data-stu-id="46c7e-210">Then, select **Delete** and then when you see the message below select **Delete** again.</span></span>

   ![Abbildung der Eingabeaufforderung, in der Sie gefragt werden, ob Sie einen geplanten Start löschen oder beibehalten möchten](../media/portal-launch-delete-2.png)

## <a name="use-the-powershell-portal-launch-scheduler"></a><span data-ttu-id="46c7e-212">Verwenden des PowerShell-Portal-Startplaners</span><span class="sxs-lookup"><span data-stu-id="46c7e-212">Use the PowerShell Portal launch scheduler</span></span>

<span data-ttu-id="46c7e-213">Das Tool SharePoint Portal-Startplanung war ursprünglich nur über [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) verfügbar und wird weiterhin über PowerShell für Kunden unterstützt, die diese Methode bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-213">The SharePoint Portal launch scheduler tool was originally only available via [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) and will continue to be supported through PowerShell for customers who prefer this method.</span></span> <span data-ttu-id="46c7e-214">Die gleichen Hinweise zu Beginn dieses Artikels gelten für beide Versionen des Portal-Startplaners.</span><span class="sxs-lookup"><span data-stu-id="46c7e-214">The same notes at the beginning of this article apply to both versions of the Portal launch scheduler.</span></span>

> [!NOTE]
> <span data-ttu-id="46c7e-215">Sie benötigen Administratorberechtigungen, um SharePoint PowerShell verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="46c7e-215">You need administrator permissions to use SharePoint PowerShell.</span></span>
> <span data-ttu-id="46c7e-216">Portalstartdetails für starts created in PowerShell will appear and can be managed in the new Portal launch scheduler tool in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="46c7e-216">Portal launch details for launches created in PowerShell will appear and can be managed in the new Portal launch scheduler tool in SharePoint.</span></span>

### <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="46c7e-217">Einrichten von Apps und Herstellen einer Verbindung mit SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="46c7e-217">App setup and connecting to SharePoint Online</span></span>

1. <span data-ttu-id="46c7e-218">[Neueste Microsoft Office SharePoint Online-Verwaltungsshell herunterladen](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="46c7e-218">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="46c7e-p118">Wenn Sie eine frühere Version der Microsoft Office SharePoint Online-Verwaltungsshell installiert haben, gehen Sie zu Programme hinzufügen oder entfernen und deinstallieren Sie "SharePoint Online-Verwaltungsshell".</span><span class="sxs-lookup"><span data-stu-id="46c7e-p118">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="46c7e-220">Wählen Sie auf der Seite Download Center Ihre Sprache aus, und klicken Sie dann auf „Herunterladen“.</span><span class="sxs-lookup"><span data-stu-id="46c7e-220">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="46c7e-221">Wählen Sie eine x64- oder eine x86-MSI-Datei aus.</span><span class="sxs-lookup"><span data-stu-id="46c7e-221">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="46c7e-222">Laden Sie die x64-Datei herunter, wenn Sie mit der 64-Bit-Version von Windows arbeiten, oder die x86-Datei, wenn Sie mit der 32-Bit-Version arbeiten.</span><span class="sxs-lookup"><span data-stu-id="46c7e-222">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="46c7e-223">Wenn Sie sich nicht sicher sind, ziehen Sie [Welche Version des Windows-Betriebssystems verwende ich?](https://support.microsoft.com/help/13443/windows-which-operating-system) zurate.</span><span class="sxs-lookup"><span data-stu-id="46c7e-223">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="46c7e-224">Nachdem die Sie die Datei heruntergeladen haben, führen Sie die Datei aus und folgen Sie den Schritten im Setup-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="46c7e-224">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="46c7e-225">Stellen Sie eine Verbindung zu Microsoft Office SharePoint Online als [Globaler Admin oder Microsoft Office SharePoint Online-Admin](/sharepoint/sharepoint-admin-role) in Microsoft 365 her.</span><span class="sxs-lookup"><span data-stu-id="46c7e-225">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="46c7e-226">Eine Anleitung dazu finden Sie unter [Erste Schritte mit der Microsoft Office SharePoint Online-Verwaltungsshell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="46c7e-226">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

### <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="46c7e-227">Anzeigen vorhandener Portalstartsetups</span><span class="sxs-lookup"><span data-stu-id="46c7e-227">View any existing portal launch setups</span></span>

<span data-ttu-id="46c7e-228">So überprüfen Sie, ob es vorhandene Portalstartkonfigurationen gibt:</span><span class="sxs-lookup"><span data-stu-id="46c7e-228">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="46c7e-229">Planen eines Portalstarts auf der Website</span><span class="sxs-lookup"><span data-stu-id="46c7e-229">Schedule a portal launch on the site</span></span>

<span data-ttu-id="46c7e-230">Die Anzahl der erforderlichen Wellen hängt von der erwarteten Startgröße ab.</span><span class="sxs-lookup"><span data-stu-id="46c7e-230">The number of waves required depends on your expected launch size.</span></span>

- <span data-ttu-id="46c7e-231">Weniger als 10.000 Benutzer: eine Welle</span><span class="sxs-lookup"><span data-stu-id="46c7e-231">Less than 10k users: One wave</span></span>
- <span data-ttu-id="46c7e-232">10.000 bis 30.000 Benutzer: Drei Wellen</span><span class="sxs-lookup"><span data-stu-id="46c7e-232">10k to 30k users: Three waves</span></span> 
- <span data-ttu-id="46c7e-233">30.000+ bis 100.000 Benutzer: Fünf Wellen</span><span class="sxs-lookup"><span data-stu-id="46c7e-233">30k+ to 100k users: Five waves</span></span>
- <span data-ttu-id="46c7e-234">Mehr als 100.000 Benutzer: Fünf Phasen, und wenden Sie sich an Ihr Microsoft-Kontoteam.</span><span class="sxs-lookup"><span data-stu-id="46c7e-234">More than 100k users: Five waves and contact your Microsoft account team</span></span>

#### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="46c7e-235">Schritte für die bidirektionale Umleitung</span><span class="sxs-lookup"><span data-stu-id="46c7e-235">Steps for bidirectional redirection</span></span>

<span data-ttu-id="46c7e-236">Bidirektionale Umleitung umfasst das Starten eines neuen modernen SharePoint Online-Portals, um ein vorhandenes SharePoint klassischen oder modernen Portal zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-236">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="46c7e-237">Benutzer in aktiven Phasen werden zur neuen Website umgeleitet, unabhängig davon, ob sie zur alten oder neuen Website navigieren.</span><span class="sxs-lookup"><span data-stu-id="46c7e-237">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="46c7e-238">Benutzer in einer nicht gestarteten Welle, die versuchen, auf die neue Website zuzugreifen, werden zurück zur alten Website umgeleitet, bis ihre Welle gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="46c7e-238">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>

<span data-ttu-id="46c7e-239">Wir unterstützen nur die Umleitung zwischen der Standardhomepage auf der alten Website und der Standardstartseite auf der neuen Website.</span><span class="sxs-lookup"><span data-stu-id="46c7e-239">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="46c7e-240">Wenn Sie Administratoren oder Besitzer haben, die Zugriff auf die alten und neuen Websites benötigen, ohne umgeleitet zu werden, stellen Sie sicher, dass sie mithilfe des Parameters aufgeführt `WaveOverrideUsers` werden.</span><span class="sxs-lookup"><span data-stu-id="46c7e-240">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="46c7e-241">So migrieren Sie Benutzer auf mehrstufige Weise von einer vorhandenen SharePoint-Website zu einer neuen SharePoint Website:</span><span class="sxs-lookup"><span data-stu-id="46c7e-241">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="46c7e-242">Führen Sie den folgenden Befehl aus, um Portalstart-Wellen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-242">Run the following command to designate portal launch waves.</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="46c7e-243">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="46c7e-243">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"},
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="46c7e-244">Vollständige Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="46c7e-244">Complete validation.</span></span> <span data-ttu-id="46c7e-245">Es kann 5 bis 10 Minuten dauern, bis die Umleitung die Konfiguration für den gesamten Dienst abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="46c7e-245">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span>

#### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="46c7e-246">Schritte für die Umleitung zu einer temporären Seite</span><span class="sxs-lookup"><span data-stu-id="46c7e-246">Steps for redirection to temporary page</span></span>

<span data-ttu-id="46c7e-247">Die temporäre Seitenumleitung sollte verwendet werden, wenn kein vorhandenes SharePoint-Portal vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="46c7e-247">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="46c7e-248">Benutzer werden auf mehrstufige Weise zu einem neuen modernen SharePoint Onlineportal geleitet.</span><span class="sxs-lookup"><span data-stu-id="46c7e-248">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="46c7e-249">Wenn sich ein Benutzer in einer Welle befindet, die nicht gestartet wurde, wird er zu einer temporären Seite (beliebige URL) umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="46c7e-249">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span>

1. <span data-ttu-id="46c7e-250">Führen Sie den folgenden Befehl aus, um Portalstart-Wellen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-250">Run the following command to designate portal launch waves.</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="46c7e-251">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="46c7e-251">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"},
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="46c7e-252">Vollständige Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="46c7e-252">Complete validation.</span></span> <span data-ttu-id="46c7e-253">Es kann 5 bis 10 Minuten dauern, bis die Umleitung die Konfiguration für den gesamten Dienst abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="46c7e-253">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span>

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="46c7e-254">Anhalten oder Neustarten eines Portalstarts auf der Website</span><span class="sxs-lookup"><span data-stu-id="46c7e-254">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="46c7e-255">Führen Sie den folgenden Befehl aus, um den Start eines Portals zu unterbrechen und vorübergehend zu verhindern, dass anstehende Welle-Progressionen auftreten:</span><span class="sxs-lookup"><span data-stu-id="46c7e-255">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="46c7e-256">Überprüfen Sie, ob alle Benutzer zur alten Website umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="46c7e-256">Validate that all users are redirected to the old site.</span></span>

3. <span data-ttu-id="46c7e-257">Führen Sie den folgenden Befehl aus, um einen angehaltenen Portalstart neu zu starten:</span><span class="sxs-lookup"><span data-stu-id="46c7e-257">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```

4. <span data-ttu-id="46c7e-258">Überprüfen Sie, ob die Umleitung jetzt wiederhergestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="46c7e-258">Validate that the redirection is now restored.</span></span>

### <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="46c7e-259">Löschen eines Portalstarts auf der Website</span><span class="sxs-lookup"><span data-stu-id="46c7e-259">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="46c7e-260">Führen Sie den folgenden Befehl aus, um ein Geplantes oder laufendes Starten eines Portals für eine Website zu löschen.</span><span class="sxs-lookup"><span data-stu-id="46c7e-260">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="46c7e-261">Überprüfen Sie, ob keine Umleitung für alle Benutzer erfolgt.</span><span class="sxs-lookup"><span data-stu-id="46c7e-261">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="46c7e-262">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46c7e-262">Learn more</span></span>

[<span data-ttu-id="46c7e-263">Planen des Rolloutplans ihres Portals in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="46c7e-263">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)

[<span data-ttu-id="46c7e-264">Planen Ihrer Kommunikationswebsite</span><span class="sxs-lookup"><span data-stu-id="46c7e-264">Plan your communication site</span></span>](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
