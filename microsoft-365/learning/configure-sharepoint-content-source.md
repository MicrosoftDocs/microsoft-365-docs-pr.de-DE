---
title: 'In Kürze: Konfigurieren von SharePoint als Lerninhaltsquelle für Microsoft Viva Learning (Vorschau)'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Erfahren Sie, wie Sie SharePoint als Lerninhaltsquelle für Microsoft Viva Learning (Vorschau) konfigurieren.
ms.openlocfilehash: 2bed3a42d62e2aab2165ee38379eb07503807e6e
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333578"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a><span data-ttu-id="54788-103">In Kürze: Konfigurieren von SharePoint als Lerninhaltsquelle für Microsoft Viva Learning (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="54788-103">Coming soon: Configure SharePoint as a learning content source for Microsoft Viva Learning (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="54788-104">Die Informationen in diesem Artikel beziehen sich auf ein Vorschauprodukt, das möglicherweise erheblich geändert wird, bevor es kommerziell veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="54788-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="54788-105">Sie können SharePoint als Lerninhaltsquelle konfigurieren, um die eigenen Inhalte Ihrer Organisation in Viva Learning (Vorschau) verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="54788-105">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (Preview).</span></span>

## <a name="overview"></a><span data-ttu-id="54788-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="54788-106">Overview</span></span>

<span data-ttu-id="54788-107">Der Wissensadministrator (oder globaler Administrator) stellt eine Website-URL zur Verfügung, zu der der Lerndienst einen leeren zentralen Speicherort – das Lern-App-Inhaltsrepository – in Form einer strukturierten SharePoint-Liste erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="54788-107">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="54788-108">Diese Liste kann von Ihrer Organisation verwendet werden, um Links zu unternehmensübergreifenden SharePoint-Ordnern zu speichern, die Lerninhalte enthalten.</span><span class="sxs-lookup"><span data-stu-id="54788-108">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="54788-109">Administratoren sind für das Sammeln und Krümmen einer Liste von URLs für Ordner verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="54788-109">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="54788-110">Diese Ordner sollten nur Inhalte enthalten, die in Viva Learning (Vorschau) verfügbar gemacht werden können.</span><span class="sxs-lookup"><span data-stu-id="54788-110">These folders should only include content that can be made available in Viva Learning (Preview).</span></span>

<span data-ttu-id="54788-111">Viva Learning (Preview) unterstützt die folgenden Dokumenttypen:</span><span class="sxs-lookup"><span data-stu-id="54788-111">Viva Learning (Preview) supports the following document types:</span></span>

- <span data-ttu-id="54788-112">Word, PowerPoint, Excel, PDF</span><span class="sxs-lookup"><span data-stu-id="54788-112">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="54788-113">Audio (.m4a)</span><span class="sxs-lookup"><span data-stu-id="54788-113">Audio (.m4a)</span></span>
- <span data-ttu-id="54788-114">Video (.mov, .mp4, .avi)</span><span class="sxs-lookup"><span data-stu-id="54788-114">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="54788-115">Weitere Informationen finden Sie unter [SharePoint-Beschränkungen](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span><span class="sxs-lookup"><span data-stu-id="54788-115">For more information, see [SharePoint limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span> 

## <a name="permissions"></a><span data-ttu-id="54788-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="54788-116">Permissions</span></span>

<span data-ttu-id="54788-117">URLs für Dokumentbibliotheksordner können von jeder beliebigen SharePoint-Website in der Organisation gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="54788-117">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="54788-118">Viva Learning (Preview) folgt allen vorhandenen Inhaltsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="54788-118">Viva Learning (Preview) follows all existing content permissions.</span></span> <span data-ttu-id="54788-119">Daher sind nur Inhalte, für die ein Benutzer Zugriffsrechte hat, in Viva Learning (Vorschau) durchsuchbar und sichtbar.</span><span class="sxs-lookup"><span data-stu-id="54788-119">Therefore, only content for which a user has permission to access is searchable and visible within Viva Learning (Preview).</span></span> <span data-ttu-id="54788-120">Alle Inhalte in diesen Ordnern sind durchsuchbar, aber nur Inhalte, für die der einzelne Mitarbeiter Berechtigungen besitzt, können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="54788-120">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="54788-121">Das Löschen von Inhalten aus dem Repository Ihrer Organisation wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="54788-121">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="54788-122">Führen Sie die folgenden Schritte aus, um unbeabsichtigt angezeigte Inhalte zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="54788-122">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="54788-123">Um den Zugriff auf die Dokumentbibliothek einzuschränken, wählen Sie **die** Option Aktionen anzeigen aus, und wählen Sie dann Zugriff **verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="54788-123">To restrict access to the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![Dokumentbibliotheksseite in SharePoint mit Option Aktionen anzeigen mit Zugriff verwalten highligted.](../media/learning/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="54788-125">Löschen Sie das ursprüngliche Dokument in der Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="54788-125">Delete the original document within the document library.</span></span>

<span data-ttu-id="54788-126">Weitere Informationen finden Sie unter [Freigabe und Berechtigungen in der modernen SharePoint-Erfahrung.](/sharepoint/modern-experience-sharing-permissions)</span><span class="sxs-lookup"><span data-stu-id="54788-126">For more information, see [Sharing and permissions in the SharePoint modern experience](/sharepoint/modern-experience-sharing-permissions).</span></span> 

## <a name="learning-service"></a><span data-ttu-id="54788-127">Lerndienst</span><span class="sxs-lookup"><span data-stu-id="54788-127">Learning Service</span></span>

<span data-ttu-id="54788-128">Der Lerndienst verwendet die bereitgestellten Ordner-URLs, um Metadaten aus allen Inhalten zu erhalten, die in diesen Ordnern gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="54788-128">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="54788-129">Innerhalb von 24 Stunden nach der Bereitstellung der Ordner-URL im zentralen Repository können Mitarbeiter innerhalb von Viva Learning (Vorschau) nach den Inhalten Ihrer Organisation suchen und diese verwenden.</span><span class="sxs-lookup"><span data-stu-id="54788-129">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (Preview).</span></span> <span data-ttu-id="54788-130">Alle Änderungen an Inhalten, einschließlich aktualisierter Metadaten und Berechtigungen, werden auch innerhalb von 24 Stunden im Lerndienst angewendet.</span><span class="sxs-lookup"><span data-stu-id="54788-130">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

## <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="54788-131">Konfigurieren von SharePoint als Quelle</span><span class="sxs-lookup"><span data-stu-id="54788-131">Configure SharePoint as a source</span></span>

<span data-ttu-id="54788-132">Sie müssen ein globaler Microsoft 365-Administrator, SharePoint-Administrator oder Wissensadministrator sein, um diese Aufgaben ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="54788-132">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="54788-133">Führen Sie die folgenden Schritte aus, um SharePoint als Lerninhaltsquellen in für Viva Learning (Preview) zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="54788-133">To configure SharePoint as a learning content sources in for Viva Learning (Preview), follow these steps:</span></span>

1.  <span data-ttu-id="54788-134">Wechseln Sie in der linken Navigation des Microsoft 365 Admin Centers zu **Einstellungen**  >  **Organisationseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="54788-134">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="54788-135">Wählen Sie **auf der** Seite Organisationseinstellungen auf der Registerkarte **Dienste** die Option Viva **Learning (Vorschau)** aus.</span><span class="sxs-lookup"><span data-stu-id="54788-135">On the **Org settings** page, on the **Services** tab, select **Viva Learning (Preview)**.</span></span>

     ![Einstellungsseite im Microsoft 365 Admin Center, auf der "Viva Learning" aufgeführt ist.](../media/learning/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="54788-137">Im **Bereich "Viva Learning(Preview)"** unter SharePoint wird die Website-URL zur SharePoint-Website angegeben, auf der Sie ein zentrales Repository von Viva Learning (Preview) erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="54788-137">On the **Viva Learning (Preview)** panel, under SharePoint, provides the site URL to the SharePoint site where you want Viva Learning (Preview) to create a centralized repository.</span></span>

     ![Lernbereich im Microsoft 365 Admin Center, in dem SharePoint ausgewählt ist.](../media/learning/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="54788-139">Eine SharePoint-Liste wird automatisch auf der bereitgestellten SharePoint-Website erstellt.</span><span class="sxs-lookup"><span data-stu-id="54788-139">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![Neu erstellte SharePoint-Liste auf der SharePoint-Website.](../media/learning/learning-sharepoint-configure3.png)

     <span data-ttu-id="54788-141">Wählen Sie im linken Navigationsbereich der SharePoint-Website **Websiteinhalte**  >  **Lern-App-Inhaltsrepository aus.**</span><span class="sxs-lookup"><span data-stu-id="54788-141">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![SharePoint-Liste mit der Navigation von Websiteinhalten und dem Abschnitt Lern-App-Inhaltsrepository.](../media/learning/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="54788-143">Füllen Sie auf der Seite Lern-App-Inhaltsrepository die SharePoint-Liste mit URLs in die Lerninhaltsordner auf. </span><span class="sxs-lookup"><span data-stu-id="54788-143">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="54788-144">Wählen **Sie Neu** aus, um den Bereich Neues Element **anzeigen** zu können.</span><span class="sxs-lookup"><span data-stu-id="54788-144">Select **New** to view the **New item** panel.</span></span> 

       ![Lerninhaltsrepository-Seite in SharePoint mit der Option Neu.](../media/learning/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="54788-146">Fügen Sie **im Bereich** Neues Element im Feld **Titel** einen Verzeichnisnamen Ihrer Wahl hinzu.</span><span class="sxs-lookup"><span data-stu-id="54788-146">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="54788-147">Fügen Sie **im Feld Ordner-URL** die URL dem Lerninhaltsordner hinzu.</span><span class="sxs-lookup"><span data-stu-id="54788-147">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="54788-148">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="54788-148">Select **Save**.</span></span>

       ![Neuer Elementbereich in SharePoint mit den Feldern Titel und Ordner-URL.](../media/learning/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="54788-150">Die **Seite Lern-App-Inhaltsrepository** wird mit den neuen Lerninhalten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="54788-150">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![Lerninhaltsrepository-Seite in SharePoint mit den aktualisierten Informationen.](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="54788-152">Um einen umfassenderen Zugriff auf das Inhaltsrepository der Lern-App zu ermöglichen, wird in Kürze ein Link zur Liste in der Benutzeroberfläche von Viva Learning (Vorschau) verfügbar sein, auf der Benutzer Zugriff anfordern und letztendlich dazu beitragen können, die Liste auffüllen zu können.</span><span class="sxs-lookup"><span data-stu-id="54788-152">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (Preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="54788-153">Websitebesitzer und globale Administratoren müssen Zugriff auf die Liste gewähren.</span><span class="sxs-lookup"><span data-stu-id="54788-153">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="54788-154">Der Zugriff ist nur für die Liste spezifisch und gilt nicht für die Website, auf der die Liste gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="54788-154">Access is specific to the list only and does not apply to the site where the list is stored.</span></span> <span data-ttu-id="54788-155">Weitere Informationen finden Sie weiter unten in diesem Artikel unter [Bereitstellen](#provide-your-own-organizations-content) der Inhalte Ihrer eigenen Organisation.</span><span class="sxs-lookup"><span data-stu-id="54788-155">For more information, see [Provide your own organization's content](#provide-your-own-organizations-content) later in this article.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="54788-156">Krümmung der Ordner-URL-Dokumentbibliothek</span><span class="sxs-lookup"><span data-stu-id="54788-156">Folder URL document library curation</span></span>

<span data-ttu-id="54788-157">Standardmetadaten (z. B. Geändertes Datum, erstellt durch, Dokumentname, Inhaltstyp und Organisationsname) werden automatisch von der Microsoft Graph-API in Viva Learning (Vorschau) gezogen.</span><span class="sxs-lookup"><span data-stu-id="54788-157">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (Preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="54788-158">Um die allgemeine Such- und Suchrelevanz des Inhalts zu verbessern, empfehlen wir das Hinzufügen einer **Beschreibungsspalte.**</span><span class="sxs-lookup"><span data-stu-id="54788-158">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="54788-159">Führen Sie **die** folgenden Schritte aus, um der Dokumentbibliotheksseite eine Beschreibungsspalte hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="54788-159">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="54788-160">Wählen Sie **auf der** Seite Dokumente die Option Spalte **hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="54788-160">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="54788-161">Wählen Sie **die Option Aktionen** anzeigen aus, und wählen Sie dann Einzelne **Textzeile aus.**</span><span class="sxs-lookup"><span data-stu-id="54788-161">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![Seite "Dokumente" in SharePoint mit den Optionen Aktionen anzeigen mit hervorgehobener Textzeile.](../media/learning/learning-sharepoint-curation1.png)

3. <span data-ttu-id="54788-163">Fügen Sie **im Bereich** Spalte erstellen im **Feld Name** einen beschreibenden Namen für die Spalte hinzu.</span><span class="sxs-lookup"><span data-stu-id="54788-163">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="54788-164">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="54788-164">Select **Save**.</span></span>

     ![Erstellen Sie einen Spaltenbereich in SharePoint mit dem Namen und anderen Feldern.](../media/learning/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="54788-166">Fügen Sie **auf** der Seite Dokumente in der **Spalte Beschreibung** benutzerdefinierte Beschreibungen für jedes Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="54788-166">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="54788-167">Wenn keine Beschreibung angegeben wird, stellt Viva Learning (Preview) eine Standardnachricht zur Verfügung, die den Inhalt als aus Ihrer eigenen SharePoint-Bibliothek hervorhebt.</span><span class="sxs-lookup"><span data-stu-id="54788-167">If no description is supplied, Viva Learning (Preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![Dokumentseite in SharePoint mit den Beschreibungen in der Spalte Beschreibung.](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a><span data-ttu-id="54788-169">Bereitstellen der Inhalte Ihrer eigenen Organisation</span><span class="sxs-lookup"><span data-stu-id="54788-169">Provide your own organization's content</span></span>

<span data-ttu-id="54788-170">Wissensadministratoren können auf das Lern-App-Inhaltsrepository ihrer Organisation in SharePoint zugreifen, wo sie Verweise auf organisationsübergreifende Dokumentbibliotheken bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="54788-170">Knowledge admins can access their organization’s Learning App Content Repository in SharePoint, where they can provide references to cross-organization document libraries.</span></span> <span data-ttu-id="54788-171">Inhalte in diesen Bibliotheken werden dann in "Viva Learning" (Vorschau) als Lerninhalte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="54788-171">Content within these libraries will be then surfaced as learning content in Viva Learning (Preview).</span></span>

1. <span data-ttu-id="54788-172">Wählen Sie in Viva Learning (Vorschau) **weitere Optionen** (**...**) aus, und wählen Sie dann **Einstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="54788-172">In Viva Learning (Preview), select **More options** (**...**), and then select **Settings**.</span></span>

     ![SharePoint-Bibliotheksseite mit der Option Weitere Optionen und Einstellungen.](../media/learning/learning-sharepoint-library-1.png)
     
2. <span data-ttu-id="54788-174">Wählen **Sie unter Einstellungen** die Option Berechtigungen **aus.**</span><span class="sxs-lookup"><span data-stu-id="54788-174">Under **Settings**, select **Permissions**.</span></span>

     ![Einstellungsoptionsseite in SharePoint mit den Zugriffsoptionen Berechtigungen und Überprüfen.](../media/learning/learning-sharepoint-library-2.png)

3. <span data-ttu-id="54788-176">Wählen **Sie Zugriff überprüfen** aus, um eine Verbindung mit der zentralen Bibliothek Ihrer Organisation herzustellen.</span><span class="sxs-lookup"><span data-stu-id="54788-176">Select **Check access** to connect to your organization’s centralized library.</span></span>
     
