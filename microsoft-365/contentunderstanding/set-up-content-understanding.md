---
title: Einrichten von SharePoint-Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Einrichten des Inhalts Verständnisses in Project Cortex
ms.openlocfilehash: 31c6b6dd31b3f1bc47deb8424dd847cc0af6d429
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304780"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="bb9c2-103">Einrichten von SharePoint-Syntex</span><span class="sxs-lookup"><span data-stu-id="bb9c2-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="bb9c2-104">Administratoren können das Microsoft 365 Admin Center zum Einrichten und Microsoft SharePoint-Syntex verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-104">Admins can use the Microsoft 365 admin center to set up and Microsoft SharePoint Syntex.</span></span> 

<span data-ttu-id="bb9c2-105">Bevor Sie beginnen, sollten Sie Folgendes in Frage stellen:</span><span class="sxs-lookup"><span data-stu-id="bb9c2-105">Consider the following before you start:</span></span>

- <span data-ttu-id="bb9c2-106">Auf welchen SharePoint-Websites wird die Formularverarbeitung aktiviert?</span><span class="sxs-lookup"><span data-stu-id="bb9c2-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="bb9c2-107">Alle, einige, oder wählen Sie Websites aus?</span><span class="sxs-lookup"><span data-stu-id="bb9c2-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="bb9c2-108">Wie lautet der Name Ihres inhaltscenters und wer ist der primäre Websiteadministrator?</span><span class="sxs-lookup"><span data-stu-id="bb9c2-108">What will you name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="bb9c2-109">Sie können Ihre Einstellungen nach dem ersten Setup im Microsoft 365 Admin Center ändern.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="bb9c2-110">Der Inhalt in diesem Artikel ist für die Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="bb9c2-111">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="bb9c2-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="bb9c2-112">Stellen Sie vor dem einrichten sicher, dass Sie die beste Möglichkeit zum Einrichten und Konfigurieren des Inhalts Verständnisses in Ihrer Umgebung planen.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="bb9c2-113">Sie müssen beispielsweise Überlegungen zu den folgenden Namen von ausführen:</span><span class="sxs-lookup"><span data-stu-id="bb9c2-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="bb9c2-114">Die SharePoint-Websites, für die die Formularverarbeitung aktiviert werden soll-alle, einige oder ausgewählte Websites</span><span class="sxs-lookup"><span data-stu-id="bb9c2-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="bb9c2-115">Ihr inhaltscenter und der Name des primären Websiteadministrators</span><span class="sxs-lookup"><span data-stu-id="bb9c2-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="bb9c2-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb9c2-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="bb9c2-117">Sie müssen über globale Administrator-oder SharePoint-Administratorberechtigungen verfügen, um auf das Microsoft 365 Admin Center zugreifen und das Verständnis für Inhalte einrichten zu können.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="bb9c2-118">Als Administrator können Sie Änderungen an Ihren ausgewählten Einstellungen jederzeit nach dem Setup und während des Inhalts Grundlegendes zu Verwaltungseinstellungen im Microsoft 365 Admin Center vornehmen.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="bb9c2-119">So richten Sie SharePoint-Syntex ein</span><span class="sxs-lookup"><span data-stu-id="bb9c2-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="bb9c2-120">Wählen Sie im Microsoft 365 Admin Center die Option **Setup**aus, und zeigen Sie dann den Abschnitt **organisatorisches Wissen** an.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>

2. <span data-ttu-id="bb9c2-121">Wählen Sie im Abschnitt **organisatorisches Wissen** die Option **Inhalts Verständnis automatisieren**aus.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-121">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![Setup Seite für organisatorisches Wissen](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="bb9c2-123">Klicken Sie auf der Seite **SharePoint-Syntex automatisieren** auf **Erste Schritte** , um den Installationsvorgang zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-123">On the **Automate SharePoint Syntex** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![Setup starten](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="bb9c2-125">Wählen Sie auf der Seite Bild Kennzeichnung aktivieren aus, ob Sie die [Bild Kennzeichnung](image-tagging.md)zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-125">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![Screenshot von Bild Kennzeichnungs Optionen](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="bb9c2-127">Auf der Seite **Formularverarbeitung konfigurieren** können Sie auswählen, ob Benutzer in der Lage sein sollen, Ai Builder zum Erstellen von Formular Verarbeitungs Modellen in bestimmten SharePoint-Dokumentbibliotheken zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-127">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="bb9c2-128">Im Menüband der Dokumentbibliothek wird eine Menüoption zur Verfügung stehen, um **ein Formular Verarbeitungsmodell** in SharePoint-Dokumentbibliotheken zu erstellen, in denen es aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-128">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="bb9c2-129">Für **welche SharePoint-Bibliotheken die Option zum Erstellen eines Formular Verarbeitungsmodells anzeigen soll**, können Sie Folgendes auswählen:</span><span class="sxs-lookup"><span data-stu-id="bb9c2-129">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="bb9c2-130">**Alle SharePoint-Bibliotheken** , um Sie allen SharePoint-Bibliotheken in Ihrer Organisation zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-130">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="bb9c2-131">**Nur Bibliotheken an ausgewählten Websites**, und wählen Sie dann die Websites aus, in denen Sie verfügbar sein sollen.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-131">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>

   ![Konfigurieren der Formularverarbeitung](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="bb9c2-133">Das Aktivieren dieser Einstellung für eine SharePoint-Dokumentbibliothek wirkt sich nicht auf vorhandene Modelle aus, die auf die Bibliothek angewendet werden, oder auf die Möglichkeit, Dokument Verständnis Modelle auf eine Bibliothek anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-133">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="bb9c2-134">Auf der Seite **inhaltscenter erstellen** können Sie eine SharePoint-inhaltscenter-Website erstellen, auf der Ihre Benutzerdokument Verständnis Modelle erstellen und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-134">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="bb9c2-135">a.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-135">a.</span></span> <span data-ttu-id="bb9c2-136">Geben Sie unter **Websitename**den Namen ein, den Sie Ihrer inhaltscenter-Website zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-136">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="bb9c2-137">b.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-137">b.</span></span> <span data-ttu-id="bb9c2-138">Die **Websiteadresse** zeigt basierend auf dem, was Sie für den Websitenamen ausgewählt haben, die URL für Ihre Website an.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-138">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="bb9c2-139">Wenn Sie Sie ändern möchten, klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-139">If you want to change it, click **Edit**.</span></span></br>

      ![Inhaltscenter erstellen](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="bb9c2-141">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-141">Select **Next**.</span></span>

7. <span data-ttu-id="bb9c2-142">Auf der Seite **überprüfen und fertig stellen** können Sie sich Ihre ausgewählte Einstellung ansehen und auswählen, dass Sie Änderungen vornehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-142">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="bb9c2-143">Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-143">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="bb9c2-144">Klicken Sie auf der Seite Bestätigung auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-144">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="bb9c2-145">Sie kehren zu Ihrer Seite zum **Automatisieren von Inhalten** zurück.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-145">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="bb9c2-146">Auf dieser Seite können Sie **Verwalten** auswählen, um Änderungen an Ihren Konfigurationseinstellungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-146">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="bb9c2-147">Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="bb9c2-147">Assign licenses</span></span>

<span data-ttu-id="bb9c2-148">Nachdem Sie die SharePoint-Syntex konfiguriert haben, müssen Sie Lizenzen für die Benutzer zuweisen, die die Formularverarbeitung und Dokument Verständnis Features verwenden sollen.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-148">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using form processing and document understanding features.</span></span>

<span data-ttu-id="bb9c2-149">So weisen Sie Lizenzen zu:</span><span class="sxs-lookup"><span data-stu-id="bb9c2-149">To assign licenses:</span></span>

1. <span data-ttu-id="bb9c2-150">Klicken Sie im Microsoft 365 Admin Center unter **Benutzer**auf **aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-150">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="bb9c2-151">Wählen Sie die Benutzer aus, die Sie lizenzieren möchten, und klicken Sie auf **Produktlizenzen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-151">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="bb9c2-152">Wählen Sie **mehr zuweisen**aus.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-152">Select **Assign more**.</span></span>

4. <span data-ttu-id="bb9c2-153">Wählen Sie **Intelligent Content Services**aus.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-153">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="bb9c2-154">Stellen Sie sicher, dass unter **apps**die Option **Common Data Service for Intelligent Content Services** und **Intelligent Content Services** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-154">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![SharePoint-Syntex-Lizenzen im Microsoft 365 Admin Center](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="bb9c2-156">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-156">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="bb9c2-157">Credits für AI Builder</span><span class="sxs-lookup"><span data-stu-id="bb9c2-157">AI Builder credits</span></span>

<span data-ttu-id="bb9c2-158">Wenn Sie 300 oder mehr SharePoint-Syntex-Lizenzen für SharePoint-Syntex in Ihrer Organisation haben, werden Ihnen 1 Million AI Builder Credits zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-158">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="bb9c2-159">Wenn Sie über weniger als 300 Lizenzen verfügen, müssen Sie die Credits von AI Builder erwerben, um die Formularverarbeitung verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-159">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="bb9c2-160">Sie können die Kapazität des AI-Generators schätzen, die für Sie mit dem [AI Builder-Rechner](https://powerapps.microsoft.com/ai-builder-calculator)geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-160">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="bb9c2-161">Wechseln Sie zum [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/resources/capacity) , um ihre Guthaben und Ihre Nutzung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="bb9c2-161">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb9c2-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb9c2-162">See also</span></span>

[<span data-ttu-id="bb9c2-163">Übersicht über das Formular Verarbeitungsmodell</span><span class="sxs-lookup"><span data-stu-id="bb9c2-163">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="bb9c2-164">Schritt-für-Schritt: Erstellen eines Dokument Verständnisses des Modells (Video)</span><span class="sxs-lookup"><span data-stu-id="bb9c2-164">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

