---
title: Einrichten von SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: Einrichten des Inhaltsverständnisses in Projekt Cortex
ms.openlocfilehash: 2f9fd4e035152a127f9f1c254f4c489a6ca4c976
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994701"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="b5a96-103">Einrichten von SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="b5a96-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="b5a96-104">Administratoren können das Microsoft 365 Admin Center verwenden, um [Microsoft SharePoint Syntex](index.md) einzurichten.</span><span class="sxs-lookup"><span data-stu-id="b5a96-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="b5a96-105">Denken Sie vor dem Beginn über Folgendes nach:</span><span class="sxs-lookup"><span data-stu-id="b5a96-105">Consider the following before you start:</span></span>

- <span data-ttu-id="b5a96-106">Auf welchen SharePoint-Websites wird die Formularverarbeitung aktiviert?</span><span class="sxs-lookup"><span data-stu-id="b5a96-106">In which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="b5a96-107">Auf allen, auf einigen oder auf ausgewählten Websites?</span><span class="sxs-lookup"><span data-stu-id="b5a96-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="b5a96-108">Wie werden Sie Ihr Standard-Inhaltscenter nennen?</span><span class="sxs-lookup"><span data-stu-id="b5a96-108">What will you name your default content center?</span></span>

<span data-ttu-id="b5a96-109">Sie können Ihre Einstellungen nach der erstmaligen Einrichtung im Microsoft 365 Admin Center ändern.</span><span class="sxs-lookup"><span data-stu-id="b5a96-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="b5a96-110">Vergewissern Sie sich vor dem Einrichten, dass Sie die beste Möglichkeit zum Einrichten und Konfigurieren des Inhaltsverständnisses in Ihrer Umgebung planen.</span><span class="sxs-lookup"><span data-stu-id="b5a96-110">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="b5a96-111">Sie müssen beispielsweise folgende Entscheidungen treffen:</span><span class="sxs-lookup"><span data-stu-id="b5a96-111">For example, you need to make the following decisions:</span></span>

- <span data-ttu-id="b5a96-112">Die SharePoint-Websites, auf denen Sie die Verarbeitung von Formularen aktivieren möchten – alle, einige oder ausgewählte Websites.</span><span class="sxs-lookup"><span data-stu-id="b5a96-112">The SharePoint sites in which you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="b5a96-113">Name und Administratoren für Ihr Inhaltscenter</span><span class="sxs-lookup"><span data-stu-id="b5a96-113">The name and admins for your content center</span></span>

## <a name="requirements"></a><span data-ttu-id="b5a96-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b5a96-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="b5a96-115">Sie müssen über globale Administrator- oder SharePoint-Administratorberechtigungen verfügen, um auf das Microsoft 365 Admin Center zugreifen und SharePoint Syntex einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="b5a96-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up SharePoint Syntex.</span></span>

<span data-ttu-id="b5a96-116">Als Administrator können Sie nach dem Einrichten und in den Verwaltungseinstellungen für das Inhaltsverständnis im Microsoft 365 Admin Center jederzeit Änderungen an den ausgewählten Einstellungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="b5a96-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

### <a name="licensing"></a><span data-ttu-id="b5a96-117">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="b5a96-117">Licensing</span></span>

<span data-ttu-id="b5a96-118">Um SharePoint Syntex verwenden zu können, muss Ihre Organisation ein entsprechendes Abonnement dafür haben, und jedem Benutzer müssen die folgenden Lizenzen zugewiesen sein:</span><span class="sxs-lookup"><span data-stu-id="b5a96-118">To use SharePoint Syntex, your organization must have a subscription to SharePoint Syntex, and each user must have the following licenses assigned:</span></span>

- <span data-ttu-id="b5a96-119">SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="b5a96-119">SharePoint Syntex</span></span>
- <span data-ttu-id="b5a96-120">SharePoint Syntex – SPO-Typ</span><span class="sxs-lookup"><span data-stu-id="b5a96-120">SharePoint Syntex - SPO type</span></span>
- <span data-ttu-id="b5a96-121">Gemeinsamer Datendienst für SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="b5a96-121">Common Data Service for SharePoint Syntex</span></span>

<span data-ttu-id="b5a96-122">Wenn Sie Ihr SharePoint Syntex-Abonnement zu einem späteren Zeitpunkt kündigen (oder wenn Ihre Testversion abläuft), können Benutzer kein Dokumentverständnis- oder Formularverarbeitungsmodell mehr erstellen oder ausführen, und die Inhaltscenter-Vorlage ist nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b5a96-122">If you cancel your SharePoint Syntex subscription at a future date (or your trial expires), users will no longer be able to create or run document understanding or form processing models, and the content center template will no longer be available.</span></span> <span data-ttu-id="b5a96-123">Zusätzlich werden Terminologiespeicher-Berichte, SKOS-Taxonomie-Importe und Inhaltstyp-Push nicht mehr verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="b5a96-123">Additionally, term store reports, SKOS taxonomy import, and Content type push will no longer be available.</span></span> <span data-ttu-id="b5a96-124">Es werden keine Inhalte gelöscht und die Websiteberechtigungen werden nicht verändert.</span><span class="sxs-lookup"><span data-stu-id="b5a96-124">No content will be deleted and site permissions will not be changed.</span></span>

### <a name="ai-builder-credits"></a><span data-ttu-id="b5a96-125">KI-Generator-Punkte</span><span class="sxs-lookup"><span data-stu-id="b5a96-125">AI Builder credits</span></span>

<span data-ttu-id="b5a96-126">Wenn Sie 300 oder mehr SharePoint Syntex-Lizenzen für SharePoint Syntex in Ihrer Organisation besitzen, werden Ihnen 1 Million KI-Generator-Punkte zugeteilt.</span><span class="sxs-lookup"><span data-stu-id="b5a96-126">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="b5a96-127">Wenn Sie weniger als 300 Lizenzen besitzen, müssen Sie KI-Generator-Punkte erwerben, um die Formularverarbeitung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5a96-127">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="b5a96-128">Sie können die für Sie geeignete KI-Generator-Kapazität mit dem [KI-Generator-Rechner](https://powerapps.microsoft.com/ai-builder-calculator) abschätzen.</span><span class="sxs-lookup"><span data-stu-id="b5a96-128">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="b5a96-129">Wenn Sie planen, eine benutzerdefinierte Power Platform-Umgebung zu verwenden, [weisen Sie dieser Umgebung Guthaben zu](/power-platform/admin/capacity-add-on).</span><span class="sxs-lookup"><span data-stu-id="b5a96-129">If you plan to use a custom Power Platform environment, you must [allocate credits to that environment](/power-platform/admin/capacity-add-on).</span></span>

<span data-ttu-id="b5a96-130">Wechseln Sie zum [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/resources/capacity), um Ihre Punkte und deren Nutzung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b5a96-130">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="b5a96-131">So richten Sie SharePoint Syntex ein</span><span class="sxs-lookup"><span data-stu-id="b5a96-131">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="b5a96-132">Wählen Sie im Microsoft 365 Admin Center **Setup** aus, und zeigen Sie dann den Abschnitt **Dateien und Inhalte** an.</span><span class="sxs-lookup"><span data-stu-id="b5a96-132">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="b5a96-133">Wählen Sie im Abschnitt **Dateien und Inhalte** > **Inhaltsverständnis automatisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="b5a96-133">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="b5a96-134">Klicken Sie auf der Seite **Inhaltsverständnis automatisieren** auf **Erste Schritte**, um den Setupvorgang zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="b5a96-134">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b5a96-135">![Setup starten](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="b5a96-135">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="b5a96-136">Auf der Seite **Formularverarbeitung konfigurieren** können Sie auswählen, ob Sie zulassen möchten, dass Benutzer Formularverarbeitungsmodelle in bestimmten SharePoint-Dokumentbibliotheken erstellen können.</span><span class="sxs-lookup"><span data-stu-id="b5a96-136">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="b5a96-137">Im Menüband "Dokumentbibliothek" wird eine Menüoption zum **Erstellen eines Formularverarbeitungsmodells** in SharePoint-Dokumentbibliotheken verfügbar, in denen es aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b5a96-137">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="b5a96-138">Für **Welche SharePoint-Bibliotheken sollen die Option zum Erstellen eines Formularverarbeitungsmodells anzeigen** können Sie Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="b5a96-138">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="b5a96-139">**Bibliotheken in allen SharePoint-Websites**, damit die Option für alle SharePoint-Bibliotheken in Ihrer Organisation verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="b5a96-139">**Libraries in all SharePoint sites** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="b5a96-140">**Bibliotheken in ausgewählten SharePoint-Websites**. Wählen Sie dann die Websites aus, auf denen Sie die Option verfügbar machen möchten, oder laden Sie eine Liste mit bis zu 50 Websites hoch.</span><span class="sxs-lookup"><span data-stu-id="b5a96-140">**Libraries in selected SharePoint sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="b5a96-141">**Keine SharePoint-Bibliotheken**, wenn Sie die Option nicht auf Websites verfügbar machen möchten (Sie können dies nach der Einrichtung ändern).</span><span class="sxs-lookup"><span data-stu-id="b5a96-141">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b5a96-142">![Konfigurieren der Websiteoptionen für die Formularverarbeitung](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="b5a96-142">![Configure form processing site options](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="b5a96-143">Wenn Sie eine Website entfernen, nachdem sie hinzugefügt wurde, hat dies keine Auswirkung auf vorhandene Modelle, die auf die Bibliotheken auf dieser Website angewendet werden, oder die Möglichkeit, Dokumentverständnismodelle auf eine Bibliothek anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b5a96-143">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
    <span data-ttu-id="b5a96-144">Wenn Sie mehrere Power Platform-Umgebungen konfiguriert haben, können Sie wählen, welche Sie für die Formularverarbeitung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b5a96-144">If you have multiple Power Platform environments configured, you can choose which one you want to use with for form processing.</span></span> <span data-ttu-id="b5a96-145">(Diese Option wird nicht angezeigt, wenn Sie nur eine Umgebung konfiguriert haben).</span><span class="sxs-lookup"><span data-stu-id="b5a96-145">(This option will not appear if you only have one environment.)</span></span>

    ![Konfigurieren der Power Platform-Optionen für die Formularverarbeitung](../media/content-understanding/setup-power-platform-env.png)

    <span data-ttu-id="b5a96-147">Für **Power Platform-Umgebung** können Sie wählen:</span><span class="sxs-lookup"><span data-stu-id="b5a96-147">For **Power Platform environment**, you can select:</span></span>
    - <span data-ttu-id="b5a96-148">**Standardumgebung verwenden**, um Ihre standardmäßige Power Platform-Umgebung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5a96-148">**Use the default environment** to use your default Power Platform environment.</span></span>
    - <span data-ttu-id="b5a96-149">**Benutzerdefinierte Umgebung verwenden**, um eine benutzerdefinierte Umgebung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5a96-149">**Use a custom environment** to use a custom environment.</span></span> <span data-ttu-id="b5a96-150">Wählen Sie die zu verwendende Umgebung aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="b5a96-150">Choose the environment that you want to use from the list.</span></span> <span data-ttu-id="b5a96-151">Sie müssen die App *KI-Generator für Project Cortex* in dieser Umgebung installieren und ihr KI-Generator-Guthaben zuweisen, bevor Sie Modelle zur Formularverarbeitung erstellen können.</span><span class="sxs-lookup"><span data-stu-id="b5a96-151">You must install the *AI Builder for Project Cortex* app in this environment and allocate AI Builder credits to it before you can create form processing models.</span></span>

    <span data-ttu-id="b5a96-152">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b5a96-152">Click **Next**.</span></span>

5. <span data-ttu-id="b5a96-153">Auf der Seite **Inhaltscenter erstellen** können Sie eine Website im SharePoint-Inhaltscenter erstellen, auf der Ihre Benutzer Modelle zum Dokumentverständnis erstellen und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="b5a96-153">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="b5a96-154">Geben Sie für den **Websitenamen** den Namen ein, den Sie Ihrer Inhaltscenter-Website zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="b5a96-154">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="b5a96-155">Die **Websiteadresse** zeigt die URL für Ihre Website basierend auf Ihrer Auswahl für den Websitenamen an.</span><span class="sxs-lookup"><span data-stu-id="b5a96-155">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="b5a96-156">Wenn Sie die Einstellungen ändern möchten, klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="b5a96-156">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="b5a96-157">![Erstellen eines Inhaltscenters](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="b5a96-157">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="b5a96-158">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="b5a96-158">Select **Next**.</span></span>

6. <span data-ttu-id="b5a96-159">Auf der Seite **Überprüfen und beenden** können Sie sich die ausgewählte Einstellung ansehen und Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="b5a96-159">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="b5a96-160">Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="b5a96-160">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="b5a96-161">Klicken Sie auf der Bestätigungsseite auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="b5a96-161">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="b5a96-162">Sie kehren zur Seite **Inhaltsverständnis automatisieren** zurück.</span><span class="sxs-lookup"><span data-stu-id="b5a96-162">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="b5a96-163">Auf dieser Seite können Sie **Verwalten** auswählen, um Änderungen an Ihren Konfigurationseinstellungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="b5a96-163">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="b5a96-164">Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="b5a96-164">Assign licenses</span></span>

<span data-ttu-id="b5a96-165">Nachdem Sie SharePoint Syntex konfiguriert haben, müssen Sie Lizenzen für die Benutzer zuweisen, die SharePoint Syntex-Features verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="b5a96-165">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="b5a96-166">So weisen Sie Lizenzen zu</span><span class="sxs-lookup"><span data-stu-id="b5a96-166">To assign licenses:</span></span>

1. <span data-ttu-id="b5a96-167">Klicken Sie im Microsoft 365 Admin Center auf **Benutzer** > **Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="b5a96-167">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="b5a96-168">Wählen Sie die Benutzer aus, denen Sie eine Lizenz zuweisen möchten, und wählen Sie **Produktlizenzen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="b5a96-168">Select the users that you want to license, and choose **Manage product licenses**.</span></span>

3. <span data-ttu-id="b5a96-169">Wählen Sie im Dropdownmenü die Option **Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="b5a96-169">Choose **Apps** from the drop-down menu.</span></span>

4. <span data-ttu-id="b5a96-170">Wählen Sie **Apps für SharePoint Syntex anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="b5a96-170">Select **Show apps for  SharePoint Syntex**.</span></span> <span data-ttu-id="b5a96-171">Stellen Sie sicher, dass unter **Apps** sowohl **Gemeinsamer Datendienst für SharePoint Syntex**, **SharePoint Syntex** wie auch **SharePoint Syntex – SPO-Typ** ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="b5a96-171">Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b5a96-172">![SharePoint Syntex-Lizenzen im Microsoft 365 Admin Center](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="b5a96-172">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="b5a96-173">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="b5a96-173">Click **Save changes**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5a96-174">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="b5a96-174">See also</span></span>

[<span data-ttu-id="b5a96-175">Übersicht über das Formularverarbeitungsmodell</span><span class="sxs-lookup"><span data-stu-id="b5a96-175">Overview of the form processing model</span></span>](/ai-builder/form-processing-model-overview)

[<span data-ttu-id="b5a96-176">Schrittweise Anleitung zum Erstellen eines Modells für das Dokumentverständnis (Video)</span><span class="sxs-lookup"><span data-stu-id="b5a96-176">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

[<span data-ttu-id="b5a96-177">Erstellen und Verwalten von Umgebungen im Power Platform Admin Center</span><span class="sxs-lookup"><span data-stu-id="b5a96-177">Create and manage environments in the Power Platform admin center</span></span>](/power-platform/admin/create-environment)
