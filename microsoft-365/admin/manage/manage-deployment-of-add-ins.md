---
title: Bereitstellen von Add-Ins im Admin Center
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Hier erfahren Sie, wie Sie Add-Ins für Benutzer und Gruppen in Ihrer Organisation mithilfe einer zentralisierten Bereitstellung im Admin Center bereitstellen können.
ms.openlocfilehash: a99847cd24853a8d3d411eed97983b66001287ff
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560727"
---
# <a name="deploy-add-ins-in-the-admin-center"></a><span data-ttu-id="491f3-103">Bereitstellen von Add-Ins im Admin Center</span><span class="sxs-lookup"><span data-stu-id="491f3-103">Deploy add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="491f3-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="491f3-104">The admin center is changing.</span></span> <span data-ttu-id="491f3-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="491f3-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="491f3-106">[] Office-Add-Ins helfen Ihnen beim Personalisieren Ihrer Dokumente und beim Optimieren der Art und Weise, wie Sie im Web auf Informationen zugreifen (lesen Sie [Erste Schritte mit Ihrem Office-Add-In](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="491f3-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="491f3-107">Als Administrator können Sie Office-Add-Ins für die Benutzer in Ihrer Organisation mithilfe des Features für die zentralisierte Bereitstellung im Microsoft 365 Admin Center bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="491f3-107">As an admin, you can deploy Office add-ins for the users in your organization by using the Centralized Deployment feature in the Microsoft 365 admin center.</span></span> <span data-ttu-id="491f3-108">Die zentrale Bereitstellung ist die empfohlene und funktionsreichste Möglichkeit für die meisten Administratoren, um Add-Ins für Benutzer und Gruppen innerhalb einer Organisation bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="491f3-108">Centralized Deployment is the recommended and most feature-rich way for most admins to deploy add-ins to users and groups within an organization.</span></span> 

<span data-ttu-id="491f3-109">Weitere Informationen zum ermitteln, ob Ihre Organisation eine zentralisierte Bereitstellung unterstützenkann, finden Sie unter [bestimmen, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert](centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="491f3-109">For more information on how to determine if your organization can support Centralized Deployment, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>

<span data-ttu-id="491f3-110">Weitere Informationen zum Verwalten von Add-Ins nach der Bereitstellung finden Sie unter [Verwalten von Add-Ins im Admin Center](manage-addins-in-the-admin-center.md) .</span><span class="sxs-lookup"><span data-stu-id="491f3-110">To learn more about managing add-ins after deployment, see [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)</span></span>
  
> [!NOTE]
>  <span data-ttu-id="491f3-111">Für Word verwenden Excel und PowerPoint einen [SharePoint-App-Katalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) zum Bereitstellen von Add-Ins für Benutzer in einer lokalen Umgebung ohne Verbindung mit Microsoft 365 und/oder Unterstützung für SharePoint-Add-Ins erforderlich.</span><span class="sxs-lookup"><span data-stu-id="491f3-111">For Word, Excel and PowerPoint use a [SharePoint App Catalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) to deploy add-ins to users in an on-premises environment with no connection to Microsoft 365 and/or support for SharePoint add-ins required.</span></span> <span data-ttu-id="491f3-112">Für Outlook verwenden Sie die Exchange-Systemsteuerung für die Bereitstellung in einer lokalen Umgebung ohne Verbindung mit Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="491f3-112">For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.</span></span>
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a><span data-ttu-id="491f3-113">Empfohlene Vorgehensweise für die Bereitstellung von Office-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="491f3-113">Recommended approach for deploying Office add-ins</span></span>

<span data-ttu-id="491f3-114">Für das Rollout von Add-Ins mithilfe eines phasenweisen Ansatzes wird Folgendes empfohlen:</span><span class="sxs-lookup"><span data-stu-id="491f3-114">To roll out add-ins by using a phased approach, we recommend the following:</span></span>
  
1. <span data-ttu-id="491f3-115">Stellen Sie das Add-In für eine kleine Gruppe von Projektbeteiligten und Mitgliedern der IT-Abteilung bereit.</span><span class="sxs-lookup"><span data-stu-id="491f3-115">Roll out the add-in to a small set of business stakeholders and members of the IT department.</span></span> <span data-ttu-id="491f3-116">Wenn die Bereitstellung erfolgreich ist, fahren Sie mit Schritt 2 fort.</span><span class="sxs-lookup"><span data-stu-id="491f3-116">If the deployment is successful, move to step 2.</span></span>
    
2. <span data-ttu-id="491f3-117">Stellen Sie das Add-in für mehr Personen innerhalb des Unternehmens bereit.</span><span class="sxs-lookup"><span data-stu-id="491f3-117">Roll out the add-in to more individuals within the business.</span></span> <span data-ttu-id="491f3-118">Werten Sie die Ergebnisse erneut aus, und fahren Sie bei erfolgreicher Ausführung mit der vollständigen Bereitstellung fort.</span><span class="sxs-lookup"><span data-stu-id="491f3-118">Again, evaluate the results and, if successful, continue with full deployment.</span></span>
    
3. <span data-ttu-id="491f3-119">Führen Sie eine vollständige Einführung für alle Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="491f3-119">Perform a full rollout to all users.</span></span>
    
<span data-ttu-id="491f3-120">Je nach Größe der Zielgruppe können Sie die Roll-out-Schritte hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="491f3-120">Depending on the size of the target audience, you can add or remove roll-out steps.</span></span>
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a><span data-ttu-id="491f3-121">Bereitstellen eines Office-Add-Ins mithilfe des Admin Centers</span><span class="sxs-lookup"><span data-stu-id="491f3-121">Deploy an Office add-in using the admin center</span></span>

<span data-ttu-id="491f3-122">Bevor Sie beginnen, lesen Sie [ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert](centralized-deployment-of-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="491f3-122">Before you begin, see [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).</span></span>
  
1. <span data-ttu-id="491f3-123">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> **-Add-ins** .</span><span class="sxs-lookup"><span data-stu-id="491f3-123">In the admin center, go to the **Settings** \> **Add-ins** page.</span></span>
    
2. <span data-ttu-id="491f3-124">Wählen Sie oben auf der Seite **Add-in bereitstellen** aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="491f3-124">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>
    
3. <span data-ttu-id="491f3-125">Wählen Sie eine Option aus und folgen Sie den Anweisungen. </span><span class="sxs-lookup"><span data-stu-id="491f3-125">Select an option and follow the instructions.</span></span>
  
4. <span data-ttu-id="491f3-126">Wenn Sie die Option zum Hinzufügen eines Add-Ins aus dem Office Store ausgewählt haben, müssen Sie die Add-in-Auswahl vornehmen.</span><span class="sxs-lookup"><span data-stu-id="491f3-126">If you selected the option to add an add-in from the Office Store, make your add-in selection.</span></span> </br>

    <span data-ttu-id="491f3-127">Sie können die verfügbaren Add-Ins nach Kategorien anzeigen: **vorgeschlagen für Sie**, **Bewertung**oder **Name**.</span><span class="sxs-lookup"><span data-stu-id="491f3-127">You can view available add-ins by categories: **Suggested for you**, **Rating**, or **Name**.</span></span> <span data-ttu-id="491f3-128">In der Office Store sind nur ﻿kostenlose Add-Ins verfügbar.</span><span class="sxs-lookup"><span data-stu-id="491f3-128">Only free add-ins are available from the Office Store.</span></span> <span data-ttu-id="491f3-129">Kostenpflichtige Add-Ins werden derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="491f3-129">Paid add-ins aren't supported currently.</span></span> <span data-ttu-id="491f3-130">Nachdem Sie ein Add-in ausgewählt haben, akzeptieren Sie die Bedingungen, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="491f3-130">After you select an add-in, accept the terms and conditions to proceed.</span></span> <br/> 

    > [!NOTE] 
    > <span data-ttu-id="491f3-131">Mit der Office Store Option werden Updates und Verbesserungen automatisch für Benutzer durchgestellten.</span><span class="sxs-lookup"><span data-stu-id="491f3-131">With the Office Store option, updates and enhancements are automatically to users.</span></span>

5. <span data-ttu-id="491f3-132">Wählen Sie auf der nächsten Seite \*\* Alle \*\*, **Bestimmte Benutzer/Gruppen** oder **Nur ich** aus, um anzugeben, für wen das Add-in bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="491f3-132">On the next page, select **Everyone**, **Specific users/groups**, or **Just me** to specify who the add-in is deployed to.</span></span> <span data-ttu-id="491f3-133">Suchen Sie im Suchfeld nach bestimmten Benutzern oder Gruppen.</span><span class="sxs-lookup"><span data-stu-id="491f3-133">Use the Search box to find specific users or groups.</span></span> <br/>

    > [!NOTE] 
    > <span data-ttu-id="491f3-134">Weitere Informationen zu anderen Status, die für ein Add-in gelten, finden Sie unter [Add-in States](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).</span><span class="sxs-lookup"><span data-stu-id="491f3-134">To learn about other states that apply to an add-in, see [Add-in states](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).</span></span>
  
6. <span data-ttu-id="491f3-135">Wählen Sie **Bereitstellen**.</span><span class="sxs-lookup"><span data-stu-id="491f3-135">Select **Deploy**.</span></span>
  
7. <span data-ttu-id="491f3-136">Wenn das Add-in bereitgestellt wird, wird ein grünes Häkchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="491f3-136">A green tick appears when the add-in is deployed.</span></span> <span data-ttu-id="491f3-137">Befolgen Sie die Anweisungen auf der Seite, um das Add-in zu testen.</span><span class="sxs-lookup"><span data-stu-id="491f3-137">Follow the on-page instructions to test the add-in.</span></span>

    > [!NOTE]
    > <span data-ttu-id="491f3-138">Benutzer müssen Office möglicherweise neu starten, um das Add-in-Symbol auf dem App-Menüband anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="491f3-138">Users might need to relaunch Office to view the add-in icon on the app ribbon.</span></span> <span data-ttu-id="491f3-139">Outlook-Add-Ins können bis zu 24 Stunden dauern, bis Sie auf App-menübändern angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="491f3-139">Outlook add-ins can take up to 24 hours to appear on app ribbons.</span></span>
    
8. <span data-ttu-id="491f3-140">Wenn Sie fertig sind, wählen Sie **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="491f3-140">When finished, select **Next**.</span></span> <span data-ttu-id="491f3-141">Wenn Sie nur für sich selbst bereitgestellt haben, können Sie ändern auswählen, **der Zugriff auf das Add-in hat** , um mehr Benutzern bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="491f3-141">If you've deployed to just yourself, you can select **Change who has access to add-in** to deploy to more users.</span></span>

    <span data-ttu-id="491f3-142">Wenn Sie das Add-in für andere Mitglieder Ihrer Organisation bereitgestellt haben, befolgen Sie die Anweisungen, um die Bereitstellung des Add-ins anzukündigen.</span><span class="sxs-lookup"><span data-stu-id="491f3-142">If you've deployed the add-in to other members of your organization, follow the instructions to announce the deployment of the add-in.</span></span> <br/>
  
    <span data-ttu-id="491f3-143">Es wird empfohlen, Benutzer und Gruppen darüber zu informieren, dass das bereitgestellte Add-in verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="491f3-143">It's good practice to inform users and groups that the deployed add-in is available.</span></span> <span data-ttu-id="491f3-144">Sie sollten eine e-Mail senden, in der beschrieben wird, wann und wie das Add-in verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="491f3-144">Consider sending an email that describes when and how to use the add-in.</span></span> <span data-ttu-id="491f3-145">Einschließen oder Verknüpfen von Hilfeinhalten oder FAQs, die Benutzern helfen können, wenn Probleme mit dem Add-in auftreten.</span><span class="sxs-lookup"><span data-stu-id="491f3-145">Include or link to Help content or FAQs that might help users if they have problems with the add-in.</span></span>
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a><span data-ttu-id="491f3-146">Überlegungen beim Zuweisen eines Add-Ins zu Benutzern und Gruppen</span><span class="sxs-lookup"><span data-stu-id="491f3-146">Considerations when assigning an add-in to users and groups</span></span>

<span data-ttu-id="491f3-147">Administratoren können jedem oder bestimmten Benutzern und Gruppen ein Add-In zuweisen.</span><span class="sxs-lookup"><span data-stu-id="491f3-147">Admins can assign an add-in to everyone or to specific users and groups.</span></span> <span data-ttu-id="491f3-148">Jede Option hat Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="491f3-148">Each option has implications:</span></span>
  
- <span data-ttu-id="491f3-149">**Jeder Benutzer** Mit dieser Option wird das Add-in allen Benutzern in der Organisation zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="491f3-149">**Everyone** This option assigns the add-in to every user in the organization.</span></span> <span data-ttu-id="491f3-150">Verwenden Sie diese Option nur in Ausnahmefällen, da sie wirklich die gesamte Organisation betrifft.</span><span class="sxs-lookup"><span data-stu-id="491f3-150">Use this option sparingly and only for add-ins that are truly universal to your organization.</span></span> 
    
- <span data-ttu-id="491f3-151">**Benutzer** Wenn Sie ein Add-in einem einzelnen Benutzer zuweisen und dann das Add-in für einen neuen Benutzer bereitstellen, müssen Sie zuerst den neuen Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="491f3-151">**Users** If you assign an add-in to an individual user, and then deploy the add-in to a new user, you must first add the new user.</span></span>
    
- <span data-ttu-id="491f3-152">**Gruppen** Wenn Sie ein Add-in einer Gruppe zuweisen, werden Benutzern, die der Gruppe hinzugefügt werden, automatisch das Add-in zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="491f3-152">**Groups** If you assign an add-in to a group, users who are added to the group are automatically assigned the add-in.</span></span> <span data-ttu-id="491f3-153">Wenn ein Benutzer aus einer Gruppe entfernt wird, verliert der Benutzer den Zugriff auf das Add-in.</span><span class="sxs-lookup"><span data-stu-id="491f3-153">When a user is removed from a group, the user loses access to the add-in.</span></span> <span data-ttu-id="491f3-154">In beiden Fällen ist vom Administrator keine weitere Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="491f3-154">In either case, no additional action is required from the admin.</span></span> 

- <span data-ttu-id="491f3-155">**Nur ich** Wenn Sie ein Add-in nur für sich selbst zuweisen, wird das Add-in nur Ihrem Konto zugewiesen, was ideal zum Testen des Add-Ins ist.</span><span class="sxs-lookup"><span data-stu-id="491f3-155">**Just me** If you assign an add-in to just yourself, the add-in is assigned to only your account, which is ideal for testing the add-in.</span></span>
    
<span data-ttu-id="491f3-156">Die richtige Option für Ihre Organisation hängt von Ihrer Konfiguration ab.</span><span class="sxs-lookup"><span data-stu-id="491f3-156">The right option for your organization depends on your configuration.</span></span> <span data-ttu-id="491f3-157">Es wird jedoch empfohlen, Zuordnungen mithilfe von Gruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="491f3-157">However, we recommend making assignments by using groups.</span></span> <span data-ttu-id="491f3-158">Als Administrator ist es möglicherweise einfacher, Add-Ins mithilfe von Gruppen zu verwalten und die Mitgliedschaft dieser Gruppen zu steuern, anstatt einzelne Benutzer jedes Mal zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="491f3-158">As an admin, you might find it easier to manage add-ins by using groups and controlling the membership of those groups rather than assigning individual users each time.</span></span> <span data-ttu-id="491f3-159">In einigen Situationen möchten Sie möglicherweise den Zugriff auf eine kleine Gruppe von Benutzern einschränken, indem Sie Benutzer manuell zuweisen, indem Sie Zuweisungen an bestimmte Benutzer vornehmen.</span><span class="sxs-lookup"><span data-stu-id="491f3-159">In some situations, you might want to restrict access to a small set of users by making assignments to specific users by assigning users manually.</span></span>
  
## <a name="more-about-office-add-ins-security"></a><span data-ttu-id="491f3-160">Weitere Informationen zur Sicherheit von Office-Add-ins</span><span class="sxs-lookup"><span data-stu-id="491f3-160">More about Office add-ins security</span></span>

<span data-ttu-id="491f3-p116">Office-Add-Ins sind eine Kombination aus einer XML-Manifestdatei, die einige Metadaten zum Add-In enthält, aber vor allem auf eine Webanwendung verweist, die den gesamten Code und die Logik enthält. Add-Ins können verschiedene Bereiche von Funktionen umfassen. So können Add-Ins beispielsweise Folgendes:</span><span class="sxs-lookup"><span data-stu-id="491f3-p116">Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:</span></span>
  
- <span data-ttu-id="491f3-164">Daten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="491f3-164">Display data.</span></span>
    
- <span data-ttu-id="491f3-165">Das Dokument eines Benutzers lesen, um kontextbezogene Dienste zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="491f3-165">Read a user's document to provide contextual services.</span></span>
    
- <span data-ttu-id="491f3-166">Daten im Dokument eines Benutzers lesen und in das Dokument schreiben, um diesem Benutzer einen Wert zu bieten.</span><span class="sxs-lookup"><span data-stu-id="491f3-166">Read and write data to and from a user's document to provide value to that user.</span></span>
    
<span data-ttu-id="491f3-167">Weitere Informationen zu den Typen und Funktionen von Office-Add-Ins finden Sie unter [Office-Add-Ins-Plattformübersicht](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins), insbesondere im Abschnitt "Aufbau eines Office-Add-In".</span><span class="sxs-lookup"><span data-stu-id="491f3-167">For more information about the types and capabilities of Office add-ins, see [Office Add-ins platform overview](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins), especially the section "Anatomy of an Office Add-in."</span></span>
  
<span data-ttu-id="491f3-p117">Zur Interaktion mit dem Dokument des Benutzers muss das Add-In die erforderlichen Berechtigungen im Manifest deklarieren. Ein 5-stufiges JavaScript-API-Zugriffsberechtigungsmodell bildet die Grundlage für Datenschutz und Sicherheit für Benutzer der Aufgabenbereich-Add-Ins. Der Großteil der Add-Ins im Office Store weist die Berechtigungsstufe "ReadWriteDocument" auf, und fast alle Add-Ins unterstützen mindestens die Stufe "ReadDocument". Weitere Informationen zu den Berechtigungsstufen finden Sie unter [Anfordern von Berechtigungen zur API-Verwendung in Inhalts- und Aufgabenbereich-Add-Ins](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span><span class="sxs-lookup"><span data-stu-id="491f3-p117">To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).</span></span>
  
<span data-ttu-id="491f3-p118">Beim Aktualisieren eines Manifests werden in der Regel Änderungen am Symbol und Text eines Add-Ins vorgenommen. Gelegentlich ändern sich auch Add-In-Befehle. Die Berechtigungen des Add-Ins ändern sich jedoch nicht. Die Webanwendung, in der der gesamte Code und die Logik für das Add-In ausgeführt werden, kann sich jederzeit ändern. Dies liegt in der Natur von Webanwendungen.</span><span class="sxs-lookup"><span data-stu-id="491f3-p118">When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.</span></span>
  
<span data-ttu-id="491f3-175">Aktualisierungen für Add-Ins werden auf folgende Weise ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="491f3-175">Updates for add-ins happen as follows:</span></span>
  
- <span data-ttu-id="491f3-p119">**Line-of-Business-Add-In:** In diesem Fall, in dem ein Administrator ein Manifest explizit hochgeladen hat, erfordert das Add-In, dass der Administrator eine neue Manifestdatei zur Unterstützung von Metadatenänderungen hochlädt. Beim nächsten Starten der jeweiligen Office-Anwendungen wird das Add-In aktualisiert. Die Webanwendung kann sich jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="491f3-p119">**Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="491f3-179">Administratoren müssen ein Lob-Add-in nicht für eine Aktualisierung entfernen.</span><span class="sxs-lookup"><span data-stu-id="491f3-179">Admin does not need to remove a LOB Add-in for doing an update.</span></span>   <span data-ttu-id="491f3-180">Im Abschnitt Add-Ins kann der Administrator einfach auf das Lob-Add-in klicken und die **Schaltfläche Aktualisieren** in der unteren rechten Ecke auswählen.</span><span class="sxs-lookup"><span data-stu-id="491f3-180">In the Add-ins section, Admin can simply click on the LOB Add-in and choose the **Update Button** in the bottom right corner.</span></span> <span data-ttu-id="491f3-181">Das Update funktioniert nur, wenn die Version des neuen Add-ins größer ist als das des vorhandenen Add-Ins.</span><span class="sxs-lookup"><span data-stu-id="491f3-181">Update will work only if the version of the new add-in is greater than that of the existing add-in.</span></span>   
    
- <span data-ttu-id="491f3-p121">**Office Store-Add-In:** Wenn ein Administrator ein Add-In aus dem Office Store ausgewählt hat und dieses Add-In im Office Store aktualisiert wird, wird das Add-In später in der zentralen Bereitstellung aktualisiert. Beim nächsten Starten der jeweiligen Office-Anwendungen wird das Add-In aktualisiert. Die Webanwendung kann sich jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="491f3-p121">**Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.</span></span> 
  
## <a name="learn-more"></a><span data-ttu-id="491f3-185">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="491f3-185">Learn more</span></span>

[<span data-ttu-id="491f3-186">Verwalten von Add-Ins im Admin Center</span><span class="sxs-lookup"><span data-stu-id="491f3-186">Manage add-ins in the admin center</span></span>](manage-addins-in-the-admin-center.md)

<span data-ttu-id="491f3-187">[Erstellen Office-Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins-fundamentals).</span><span class="sxs-lookup"><span data-stu-id="491f3-187">[Building Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins-fundamentals).</span></span>

[<span data-ttu-id="491f3-188">Minderjährige und Erwerb von Add-Ins aus dem Store</span><span class="sxs-lookup"><span data-stu-id="491f3-188">Minors and acquiring add-ins from the store</span></span>](minors-and-acquiring-addins-from-the-store.md)
  
[<span data-ttu-id="491f3-189">Verwenden von PowerShell-Cmdlets für zentralisierte Bereitstellung zum Verwalten von Add-ins</span><span class="sxs-lookup"><span data-stu-id="491f3-189">Use Centralized Deployment PowerShell cmdlets to manage add-ins</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[<span data-ttu-id="491f3-190">Problembehandlung: Benutzer können keine Add-Ins sehen</span><span class="sxs-lookup"><span data-stu-id="491f3-190">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
