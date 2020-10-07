---
title: Einrichten von SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: MET150
localization_priority: Priority
description: Einrichten des Inhaltsverständnisses in Projekt Cortex
ms.openlocfilehash: 0d66076c93eb46ca11977cea12417c0816e0d11b
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367931"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="73643-103">Einrichten von SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="73643-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="73643-104">Administratoren können das Microsoft 365 Admin Center verwenden, um [Microsoft SharePoint Syntex](document-understanding-overview.md) einzurichten.</span><span class="sxs-lookup"><span data-stu-id="73643-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](document-understanding-overview.md).</span></span> 

<span data-ttu-id="73643-105">Denken Sie vor dem Beginn über Folgendes nach:</span><span class="sxs-lookup"><span data-stu-id="73643-105">Consider the following before you start:</span></span>

- <span data-ttu-id="73643-106">Auf welchen SharePoint-Websites wird die Formularverarbeitung aktiviert?</span><span class="sxs-lookup"><span data-stu-id="73643-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="73643-107">Auf allen, auf einigen oder auf ausgewählten Websites?</span><span class="sxs-lookup"><span data-stu-id="73643-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="73643-108">Wie werden Sie Ihr Standard-Inhaltscenter nennen?</span><span class="sxs-lookup"><span data-stu-id="73643-108">What will you name of your default content center?</span></span>

<span data-ttu-id="73643-109">Sie können Ihre Einstellungen nach der erstmaligen Einrichtung im Microsoft 365 Admin Center ändern.</span><span class="sxs-lookup"><span data-stu-id="73643-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="73643-110">Der Inhalt in diesem Artikel richtet sich an die private Vorschau von Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="73643-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="73643-111">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="73643-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="73643-112">Vergewissern Sie sich vor dem Einrichten, dass Sie die beste Möglichkeit zum Einrichten und Konfigurieren des Inhaltsverständnisses in Ihrer Umgebung planen.</span><span class="sxs-lookup"><span data-stu-id="73643-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="73643-113">Sie müssen sich beispielsweise Gedanken über die Benennung von Folgendem machen:</span><span class="sxs-lookup"><span data-stu-id="73643-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="73643-114">Die SharePoint-Websites, für die Sie die Verarbeitung von Formularen aktivieren möchten – alle, einige oder ausgewählte Websites.</span><span class="sxs-lookup"><span data-stu-id="73643-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="73643-115">Ihr Inhaltscenter und der Name des primären Website-Administrators.</span><span class="sxs-lookup"><span data-stu-id="73643-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="73643-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="73643-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="73643-117">Sie müssen über globale Administrator- oder SharePoint-Administratorberechtigungen verfügen, um auf das Microsoft 365 Admin Center zugreifen und das Inhaltsverständnis einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="73643-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="73643-118">Als Administrator können Sie nach dem Einrichten und in den Verwaltungseinstellungen für das Inhaltsverständnis im Microsoft 365 Admin Center jederzeit Änderungen an den ausgewählten Einstellungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="73643-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="73643-119">So richten Sie SharePoint Syntex ein</span><span class="sxs-lookup"><span data-stu-id="73643-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="73643-120">Wählen Sie im Microsoft 365 Admin Center **Setup**aus, und zeigen Sie dann den Abschnitt **Dateien und Inhalte** an.</span><span class="sxs-lookup"><span data-stu-id="73643-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="73643-121">Wählen Sie im Abschnitt **Dateien und Inhalte** > **Inhaltsverständnis automatisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="73643-121">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="73643-122">Klicken Sie auf der Seite **Inhaltsverständnis automatisieren** auf **Erste Schritte**, um den Setupvorgang zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="73643-122">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![Setup starten](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="73643-124">Wählen Sie auf der Seite zum Aktivieren der Bildkennzeichnung aus, ob Sie die [Bildkennzeichnung](image-tagging.md) zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="73643-124">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![Screenshot der Optionen für die Bildkennzeichnung](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="73643-126">Auf der Seite **Formularverarbeitung konfigurieren** können Sie auswählen, ob Sie zulassen möchten, dass Benutzer Formularverarbeitungsmodelle in bestimmten SharePoint-Dokumentbibliotheken erstellen können.</span><span class="sxs-lookup"><span data-stu-id="73643-126">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="73643-127">Im Menüband "Dokumentbibliothek" wird eine Menüoption zum **Erstellen eines Formularverarbeitungsmodells** in SharePoint-Dokumentbibliotheken verfügbar, in denen es aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="73643-127">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="73643-128">Für **Welche SharePoint-Bibliotheken sollen die Option zum Erstellen eines Formularverarbeitungsmodells anzeigen** können Sie Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="73643-128">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="73643-129">**Alle SharePoint-Bibliotheken**, damit die Option für alle SharePoint-Bibliotheken in Ihrer Organisation verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="73643-129">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="73643-130">**Nur Bibliotheken in ausgewählten Websites**. Wählen Sie dann die Websites aus, auf denen Sie die Option verfügbar machen möchten, oder laden Sie eine Liste mit bis zu 50 Websites hoch.</span><span class="sxs-lookup"><span data-stu-id="73643-130">**Only libraries in selected sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="73643-131">**Keine SharePoint-Bibliotheken**, wenn Sie die Option nicht auf Websites verfügbar machen möchten (Sie können dies nach der Einrichtung ändern).</span><span class="sxs-lookup"><span data-stu-id="73643-131">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   ![Konfigurieren der Formularverarbeitung](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="73643-133">Wenn Sie eine Website entfernen, nachdem sie hinzugefügt wurde, hat dies keine Auswirkung auf vorhandene Modelle, die auf die Bibliotheken auf dieser Website angewendet werden, oder die Möglichkeit, Dokumentverständnismodelle auf eine Bibliothek anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="73643-133">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="73643-p105">Auf der Seite **Inhaltscenter erstellen** können Sie eine Website im SharePoint-Inhaltscenter erstellen, auf der Ihre Benutzer Modelle zum Dokumentverständnis erstellen und verwalten können. </span><span class="sxs-lookup"><span data-stu-id="73643-p105">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models. </span></span></br>
    <span data-ttu-id="73643-135">a.</span><span class="sxs-lookup"><span data-stu-id="73643-135">a.</span></span> <span data-ttu-id="73643-136">Geben Sie für den **Websitenamen** den Namen ein, den Sie Ihrer Inhaltscenter-Website zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="73643-136">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="73643-137">b.</span><span class="sxs-lookup"><span data-stu-id="73643-137">b.</span></span> <span data-ttu-id="73643-138">Die **Websiteadresse** zeigt die URL für Ihre Website basierend auf Ihrer Auswahl für den Websitenamen an.</span><span class="sxs-lookup"><span data-stu-id="73643-138">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="73643-139">Wenn Sie die Einstellungen ändern möchten, klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="73643-139">If you want to change it, click **Edit**.</span></span></br>

      ![Erstellen eines Inhaltscenters](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="73643-141">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="73643-141">Select **Next**.</span></span>

7. <span data-ttu-id="73643-142">Auf der Seite **Überprüfen und beenden** können Sie sich die ausgewählte Einstellung ansehen und Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="73643-142">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="73643-143">Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="73643-143">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="73643-144">Klicken Sie auf der Bestätigungsseite auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="73643-144">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="73643-145">Sie kehren zur Seite **Inhaltsverständnis automatisieren** zurück.</span><span class="sxs-lookup"><span data-stu-id="73643-145">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="73643-146">Auf dieser Seite können Sie **Verwalten** auswählen, um Änderungen an Ihren Konfigurationseinstellungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="73643-146">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="73643-147">Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="73643-147">Assign licenses</span></span>

<span data-ttu-id="73643-148">Nachdem Sie SharePoint Syntex konfiguriert haben, müssen Sie Lizenzen für die Benutzer zuweisen, die SharePoint Syntex-Features verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="73643-148">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="73643-149">So weisen Sie Lizenzen zu</span><span class="sxs-lookup"><span data-stu-id="73643-149">To assign licenses:</span></span>

1. <span data-ttu-id="73643-150">Klicken Sie im Microsoft 365 Admin Center auf **Benutzer** > **Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="73643-150">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="73643-151">Wählen Sie die Benutzer aus, denen Sie eine Lizenz zuweisen möchten, und klicken Sie dann auf **Produktlizenzen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="73643-151">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="73643-152">Wählen Sie **Weitere zuweisen** aus.</span><span class="sxs-lookup"><span data-stu-id="73643-152">Select **Assign more**.</span></span>

4. <span data-ttu-id="73643-153">Wählen Sie **Intelligente Inhaltsdienste** aus.</span><span class="sxs-lookup"><span data-stu-id="73643-153">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="73643-154">Stellen Sie sicher, dass unter **Apps** die Optionen **Common Data Service für intelligente Inhaltsdienste** und **Intelligente Inhaltsdienste** aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="73643-154">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![SharePoint Syntex-Lizenzen im Microsoft 365 Admin Center](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="73643-156">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="73643-156">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="73643-157">KI-Generator-Punkte</span><span class="sxs-lookup"><span data-stu-id="73643-157">AI Builder credits</span></span>

<span data-ttu-id="73643-158">Wenn Sie 300 oder mehr SharePoint Syntex-Lizenzen für SharePoint Syntex in Ihrer Organisation besitzen, werden Ihnen 1 Million KI-Generator-Punkte zugeteilt.</span><span class="sxs-lookup"><span data-stu-id="73643-158">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="73643-159">Wenn Sie weniger als 300 Lizenzen besitzen, müssen Sie KI-Generator-Punkte erwerben, um die Formularverarbeitung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="73643-159">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="73643-160">Sie können die für Sie geeignete KI-Generator-Kapazität mit dem [KI-Generator-Rechner](https://powerapps.microsoft.com/ai-builder-calculator) abschätzen.</span><span class="sxs-lookup"><span data-stu-id="73643-160">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="73643-161">Wechseln Sie zum [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/resources/capacity), um Ihre Punkte und deren Nutzung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="73643-161">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="73643-162">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="73643-162">See also</span></span>

[<span data-ttu-id="73643-163">Übersicht über das Formularverarbeitungsmodell</span><span class="sxs-lookup"><span data-stu-id="73643-163">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="73643-164">Schrittweise Anleitung zum Erstellen eines Modells für das Dokumentverständnis (Video)</span><span class="sxs-lookup"><span data-stu-id="73643-164">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

