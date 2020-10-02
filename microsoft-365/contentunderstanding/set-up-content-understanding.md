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
ms.openlocfilehash: 7fb5998729c9f11902f8fdfaffa62b160928077c
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321349"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="18a93-103">Einrichten von SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="18a93-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="18a93-104">Administratoren können das Microsoft 365 Admin Center verwenden, um [Microsoft SharePoint Syntex](document-understanding-overview.md) einzurichten.</span><span class="sxs-lookup"><span data-stu-id="18a93-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](document-understanding-overview.md).</span></span> 

<span data-ttu-id="18a93-105">Denken Sie vor dem Beginn über Folgendes nach:</span><span class="sxs-lookup"><span data-stu-id="18a93-105">Consider the following before you start:</span></span>

- <span data-ttu-id="18a93-106">Auf welchen SharePoint-Websites wird die Formularverarbeitung aktiviert?</span><span class="sxs-lookup"><span data-stu-id="18a93-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="18a93-107">Auf allen, auf einigen oder auf ausgewählten Websites?</span><span class="sxs-lookup"><span data-stu-id="18a93-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="18a93-108">Wie werden Sie Ihr Standard-Inhaltscenter nennen?</span><span class="sxs-lookup"><span data-stu-id="18a93-108">What will you name of your default content center?</span></span>

<span data-ttu-id="18a93-109">Sie können Ihre Einstellungen nach der erstmaligen Einrichtung im Microsoft 365 Admin Center ändern.</span><span class="sxs-lookup"><span data-stu-id="18a93-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="18a93-110">Der Inhalt in diesem Artikel richtet sich an die private Vorschau von Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="18a93-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="18a93-111">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="18a93-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="18a93-112">Vergewissern Sie sich vor dem Einrichten, dass Sie die beste Möglichkeit zum Einrichten und Konfigurieren des Inhaltsverständnisses in Ihrer Umgebung planen.</span><span class="sxs-lookup"><span data-stu-id="18a93-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="18a93-113">Sie müssen sich beispielsweise Gedanken über die Benennung von Folgendem machen:</span><span class="sxs-lookup"><span data-stu-id="18a93-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="18a93-114">Die SharePoint-Websites, für die Sie die Verarbeitung von Formularen aktivieren möchten – alle, einige oder ausgewählte Websites.</span><span class="sxs-lookup"><span data-stu-id="18a93-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="18a93-115">Ihr Inhaltscenter und der Name des primären Website-Administrators.</span><span class="sxs-lookup"><span data-stu-id="18a93-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="18a93-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="18a93-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="18a93-117">Sie müssen über globale Administrator- oder SharePoint-Administratorberechtigungen verfügen, um auf das Microsoft 365 Admin Center zugreifen und das Inhaltsverständnis einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="18a93-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="18a93-118">Als Administrator können Sie nach dem Einrichten und in den Verwaltungseinstellungen für das Inhaltsverständnis im Microsoft 365 Admin Center jederzeit Änderungen an den ausgewählten Einstellungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="18a93-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="18a93-119">So richten Sie SharePoint Syntex ein</span><span class="sxs-lookup"><span data-stu-id="18a93-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="18a93-120">Wählen Sie im Microsoft 365 Admin Center **Setup**aus, und zeigen Sie dann den Abschnitt **Organisationswissen** an.</span><span class="sxs-lookup"><span data-stu-id="18a93-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>

2. <span data-ttu-id="18a93-121">Klicken Sie unter **Organisationswissen** auf **Inhaltsverständnis automatisieren**.</span><span class="sxs-lookup"><span data-stu-id="18a93-121">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![Setupseite des Organisationswissens](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="18a93-123">Klicken Sie auf der Seite **Inhaltsverständnis automatisieren** auf **Erste Schritte**, um den Setupvorgang zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="18a93-123">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![Setup starten](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="18a93-125">Wählen Sie auf der Seite zum Aktivieren der Bildkennzeichnung aus, ob Sie die [Bildkennzeichnung](image-tagging.md) zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="18a93-125">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![Screenshot der Optionen für die Bildkennzeichnung](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="18a93-127">Auf der Seite **Formularverarbeitung konfigurieren** können Sie auswählen, ob Sie zulassen möchten, dass Benutzer Formularverarbeitungsmodelle in bestimmten SharePoint-Dokumentbibliotheken erstellen können.</span><span class="sxs-lookup"><span data-stu-id="18a93-127">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="18a93-128">Im Menüband "Dokumentbibliothek" wird eine Menüoption zum **Erstellen eines Formularverarbeitungsmodells** in SharePoint-Dokumentbibliotheken verfügbar, in denen es aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="18a93-128">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="18a93-129">Für **Welche SharePoint-Bibliotheken sollen die Option zum Erstellen eines Formularverarbeitungsmodells anzeigen** können Sie Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="18a93-129">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="18a93-130">**Alle SharePoint-Bibliotheken**, damit die Option für alle SharePoint-Bibliotheken in Ihrer Organisation verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="18a93-130">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="18a93-131">**Nur Bibliotheken in ausgewählten Websites**. Wählen Sie dann die Websites aus, auf denen Sie die Option verfügbar machen möchten, oder laden Sie eine Liste mit bis zu 50 Websites hoch.</span><span class="sxs-lookup"><span data-stu-id="18a93-131">**Only libraries in selected sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="18a93-132">**Keine SharePoint-Bibliotheken**, wenn Sie die Option nicht auf Websites verfügbar machen möchten (Sie können dies nach der Einrichtung ändern).</span><span class="sxs-lookup"><span data-stu-id="18a93-132">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   ![Konfigurieren der Formularverarbeitung](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="18a93-134">Wenn Sie eine Website entfernen, nachdem sie hinzugefügt wurde, hat dies keine Auswirkung auf vorhandene Modelle, die auf die Bibliotheken auf dieser Website angewendet werden, oder die Möglichkeit, Dokumentverständnismodelle auf eine Bibliothek anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="18a93-134">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="18a93-135">Auf der Seite **Inhaltscenter erstellen** können Sie eine Website im SharePoint-Inhaltscenter erstellen, auf der Ihre Benutzer Modelle zum Dokumentverständnis erstellen und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="18a93-135">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="18a93-136">a.</span><span class="sxs-lookup"><span data-stu-id="18a93-136">a.</span></span> <span data-ttu-id="18a93-137">Geben Sie für den **Websitenamen** den Namen ein, den Sie Ihrer Inhaltscenter-Website zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="18a93-137">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="18a93-138">b.</span><span class="sxs-lookup"><span data-stu-id="18a93-138">b.</span></span> <span data-ttu-id="18a93-139">Die **Websiteadresse** zeigt die URL für Ihre Website basierend auf Ihrer Auswahl für den Websitenamen an.</span><span class="sxs-lookup"><span data-stu-id="18a93-139">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="18a93-140">Wenn Sie die Einstellungen ändern möchten, klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="18a93-140">If you want to change it, click **Edit**.</span></span></br>

      ![Erstellen eines Inhaltscenters](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="18a93-142">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="18a93-142">Select **Next**.</span></span>

7. <span data-ttu-id="18a93-143">Auf der Seite **Überprüfen und beenden** können Sie sich die ausgewählte Einstellung ansehen und Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="18a93-143">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="18a93-144">Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="18a93-144">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="18a93-145">Klicken Sie auf der Bestätigungsseite auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="18a93-145">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="18a93-146">Sie kehren zur Seite **Inhaltsverständnis automatisieren** zurück.</span><span class="sxs-lookup"><span data-stu-id="18a93-146">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="18a93-147">Auf dieser Seite können Sie **Verwalten** auswählen, um Änderungen an Ihren Konfigurationseinstellungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="18a93-147">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="18a93-148">Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="18a93-148">Assign licenses</span></span>

<span data-ttu-id="18a93-149">Nachdem Sie SharePoint Syntex konfiguriert haben, müssen Sie Lizenzen für die Benutzer zuweisen, die SharePoint Syntex-Features verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="18a93-149">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="18a93-150">So weisen Sie Lizenzen zu</span><span class="sxs-lookup"><span data-stu-id="18a93-150">To assign licenses:</span></span>

1. <span data-ttu-id="18a93-151">Klicken Sie im Microsoft 365 Admin Center auf **Benutzer** > **Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="18a93-151">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="18a93-152">Wählen Sie die Benutzer aus, denen Sie eine Lizenz zuweisen möchten, und klicken Sie dann auf **Produktlizenzen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="18a93-152">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="18a93-153">Wählen Sie **Weitere zuweisen** aus.</span><span class="sxs-lookup"><span data-stu-id="18a93-153">Select **Assign more**.</span></span>

4. <span data-ttu-id="18a93-154">Wählen Sie **Intelligente Inhaltsdienste** aus.</span><span class="sxs-lookup"><span data-stu-id="18a93-154">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="18a93-155">Stellen Sie sicher, dass unter **Apps** die Optionen **Common Data Service für intelligente Inhaltsdienste** und **Intelligente Inhaltsdienste** aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="18a93-155">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![SharePoint Syntex-Lizenzen im Microsoft 365 Admin Center](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="18a93-157">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="18a93-157">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="18a93-158">KI-Generator-Punkte</span><span class="sxs-lookup"><span data-stu-id="18a93-158">AI Builder credits</span></span>

<span data-ttu-id="18a93-159">Wenn Sie 300 oder mehr SharePoint Syntex-Lizenzen für SharePoint Syntex in Ihrer Organisation besitzen, werden Ihnen 1 Million KI-Generator-Punkte zugeteilt.</span><span class="sxs-lookup"><span data-stu-id="18a93-159">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="18a93-160">Wenn Sie weniger als 300 Lizenzen besitzen, müssen Sie KI-Generator-Punkte erwerben, um die Formularverarbeitung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="18a93-160">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="18a93-161">Sie können die für Sie geeignete KI-Generator-Kapazität mit dem [KI-Generator-Rechner](https://powerapps.microsoft.com/ai-builder-calculator) abschätzen.</span><span class="sxs-lookup"><span data-stu-id="18a93-161">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="18a93-162">Wechseln Sie zum [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/resources/capacity), um Ihre Punkte und deren Nutzung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="18a93-162">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="18a93-163">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="18a93-163">See also</span></span>

[<span data-ttu-id="18a93-164">Übersicht über das Formularverarbeitungsmodell</span><span class="sxs-lookup"><span data-stu-id="18a93-164">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="18a93-165">Schrittweise Anleitung zum Erstellen eines Modells für das Dokumentverständnis (Video)</span><span class="sxs-lookup"><span data-stu-id="18a93-165">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

