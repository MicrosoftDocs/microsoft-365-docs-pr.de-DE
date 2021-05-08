---
title: 'In Kürze: Konfigurieren SharePoint als Lerninhaltsquelle für Microsoft Viva Learning (Vorschau)'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: fc702f57b75b78ab523226ba7d8a8eb6505f2975
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244131"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a><span data-ttu-id="00cb2-103">In Kürze: Konfigurieren SharePoint als Lerninhaltsquelle für Microsoft Viva Learning (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="00cb2-103">Coming soon: Configure SharePoint as a learning content source for Microsoft Viva Learning (Preview)</span></span>

> [!NOTE]
> <span data-ttu-id="00cb2-104">Die Informationen in diesem Artikel beziehen sich auf ein Vorschauprodukt, das möglicherweise erheblich geändert wird, bevor es kommerziell veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="00cb2-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="00cb2-105">Sie können SharePoint als Lerninhaltsquelle konfigurieren, um die eigenen Inhalte Ihrer Organisation in Viva Learning (Vorschau) verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="00cb2-105">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (Preview).</span></span>

## <a name="overview"></a><span data-ttu-id="00cb2-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="00cb2-106">Overview</span></span>

<span data-ttu-id="00cb2-107">Der Wissensadministrator (oder globaler Administrator) stellt eine Website-URL zur Verfügung, zu der der Lerndienst einen leeren zentralen Speicherort – das Lern-App-Inhaltsrepository – in Form einer strukturierten SharePoint erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="00cb2-107">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="00cb2-108">Diese Liste kann von Ihrer Organisation verwendet werden, um Links zu unternehmensübergreifenden SharePoint, die Lerninhalte enthalten, zu speichern.</span><span class="sxs-lookup"><span data-stu-id="00cb2-108">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="00cb2-109">Administratoren sind für das Sammeln und Krümmen einer Liste von URLs für Ordner verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="00cb2-109">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="00cb2-110">Diese Ordner sollten nur Inhalte enthalten, die in Viva Learning (Vorschau) verfügbar gemacht werden können.</span><span class="sxs-lookup"><span data-stu-id="00cb2-110">These folders should only include content that can be made available in Viva Learning (Preview).</span></span>

<span data-ttu-id="00cb2-111">Viva Learning (Preview) unterstützt die folgenden Dokumenttypen:</span><span class="sxs-lookup"><span data-stu-id="00cb2-111">Viva Learning (Preview) supports the following document types:</span></span>

- <span data-ttu-id="00cb2-112">Word, PowerPoint, Excel, PDF</span><span class="sxs-lookup"><span data-stu-id="00cb2-112">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="00cb2-113">Audio (.m4a)</span><span class="sxs-lookup"><span data-stu-id="00cb2-113">Audio (.m4a)</span></span>
- <span data-ttu-id="00cb2-114">Video (.mov, .mp4, .avi)</span><span class="sxs-lookup"><span data-stu-id="00cb2-114">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="00cb2-115">Weitere Informationen finden Sie unter [SharePoint Limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span><span class="sxs-lookup"><span data-stu-id="00cb2-115">For more information, see [SharePoint limits](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498).</span></span> 

## <a name="permissions"></a><span data-ttu-id="00cb2-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="00cb2-116">Permissions</span></span>

<span data-ttu-id="00cb2-117">URLs für Dokumentbibliotheksordner können von allen SharePoint in der Organisation gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="00cb2-117">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="00cb2-118">Viva Learning (Preview) folgt allen vorhandenen Inhaltsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="00cb2-118">Viva Learning (Preview) follows all existing content permissions.</span></span> <span data-ttu-id="00cb2-119">Daher sind nur Inhalte, für die ein Benutzer Zugriffsrechte hat, in Viva Learning (Vorschau) durchsuchbar und sichtbar.</span><span class="sxs-lookup"><span data-stu-id="00cb2-119">Therefore, only content for which a user has permission to access is searchable and visible within Viva Learning (Preview).</span></span> <span data-ttu-id="00cb2-120">Alle Inhalte in diesen Ordnern sind durchsuchbar, aber nur Inhalte, für die der einzelne Mitarbeiter Berechtigungen besitzt, können verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00cb2-120">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="00cb2-121">Das Löschen von Inhalten aus dem Repository Ihrer Organisation wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="00cb2-121">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="00cb2-122">Führen Sie die folgenden Schritte aus, um unbeabsichtigt angezeigte Inhalte zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="00cb2-122">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="00cb2-123">Um den Zugriff auf die Dokumentbibliothek einzuschränken, wählen Sie **die** Option Aktionen anzeigen aus, und wählen Sie dann Zugriff **verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="00cb2-123">To restrict access to the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![Dokumentbibliotheksseite in SharePoint zeigt die Option Aktionen anzeigen mit Zugriff verwalten highligted.](../media/learning/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="00cb2-125">Löschen Sie das ursprüngliche Dokument in der Dokumentbibliothek.</span><span class="sxs-lookup"><span data-stu-id="00cb2-125">Delete the original document within the document library.</span></span>

<span data-ttu-id="00cb2-126">Weitere Informationen finden Sie unter [Freigabe und Berechtigungen in der modernen SharePoint.](/sharepoint/modern-experience-sharing-permissions)</span><span class="sxs-lookup"><span data-stu-id="00cb2-126">For more information, see [Sharing and permissions in the SharePoint modern experience](/sharepoint/modern-experience-sharing-permissions).</span></span> 

## <a name="learning-service"></a><span data-ttu-id="00cb2-127">Lerndienst</span><span class="sxs-lookup"><span data-stu-id="00cb2-127">Learning Service</span></span>

<span data-ttu-id="00cb2-128">Der Lerndienst verwendet die bereitgestellten Ordner-URLs, um Metadaten aus allen Inhalten zu erhalten, die in diesen Ordnern gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="00cb2-128">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="00cb2-129">Innerhalb von 24 Stunden nach der Bereitstellung der Ordner-URL im zentralen Repository können Mitarbeiter innerhalb von Viva Learning (Vorschau) nach den Inhalten Ihrer Organisation suchen und diese verwenden.</span><span class="sxs-lookup"><span data-stu-id="00cb2-129">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (Preview).</span></span> <span data-ttu-id="00cb2-130">Alle Änderungen an Inhalten, einschließlich aktualisierter Metadaten und Berechtigungen, werden auch innerhalb von 24 Stunden im Lerndienst angewendet.</span><span class="sxs-lookup"><span data-stu-id="00cb2-130">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

## <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="00cb2-131">Konfigurieren SharePoint als Quelle</span><span class="sxs-lookup"><span data-stu-id="00cb2-131">Configure SharePoint as a source</span></span>

<span data-ttu-id="00cb2-132">Sie müssen ein globaler administrator Microsoft 365 oder SharePoint oder Wissensadministrator sein, um diese Aufgaben ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="00cb2-132">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="00cb2-133">Führen Sie die folgenden SharePoint aus, um die Inhalte als Lerninhaltsquellen in für Viva Learning (Preview) zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="00cb2-133">To configure SharePoint as a learning content sources in for Viva Learning (Preview), follow these steps:</span></span>

1.  <span data-ttu-id="00cb2-134">Wechseln Sie in der linken Navigation des Microsoft 365 Admin Center zu **Einstellungen**  >  **Organisationseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="00cb2-134">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="00cb2-135">Wählen Sie **auf der** Seite Organisationseinstellungen auf der Registerkarte **Dienste** die Option Viva **Learning (Vorschau)** aus.</span><span class="sxs-lookup"><span data-stu-id="00cb2-135">On the **Org settings** page, on the **Services** tab, select **Viva Learning (Preview)**.</span></span>

     ![Einstellungen seite im Microsoft 365 Admin Center, in dem Das Viva Learning aufgeführt ist.](../media/learning/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="00cb2-137">Im **Bereich "Viva Learning(Preview)"** unter SharePoint wird die Website-URL zur SharePoint-Website angegeben, auf der Sie ein zentrales Repository von Viva Learning (Preview) erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="00cb2-137">On the **Viva Learning (Preview)** panel, under SharePoint, provides the site URL to the SharePoint site where you want Viva Learning (Preview) to create a centralized repository.</span></span>

     ![Lernbereich im Microsoft 365 Admin Center, in dem SharePoint angezeigt wird.](../media/learning/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="00cb2-139">Eine SharePoint wird automatisch innerhalb der bereitgestellten SharePoint erstellt.</span><span class="sxs-lookup"><span data-stu-id="00cb2-139">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![Neu erstellte SharePoint innerhalb der SharePoint Website.](../media/learning/learning-sharepoint-configure3.png)

     <span data-ttu-id="00cb2-141">Wählen Sie in der linken Navigationsleiste SharePoint Website **Websiteinhalte**  >  **Lern-App-Inhaltsrepository aus.**</span><span class="sxs-lookup"><span data-stu-id="00cb2-141">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![SharePoint liste mit der Navigation der Websiteinhalte und dem Abschnitt Lern-App-Inhaltsrepository.](../media/learning/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="00cb2-143">Füllen Sie **auf** der Seite Lern-App-Inhaltsrepository die Liste SharePoint den Lerninhaltsordnern mit URLs auf.</span><span class="sxs-lookup"><span data-stu-id="00cb2-143">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="00cb2-144">Wählen **Sie Neu** aus, um den Bereich Neues Element **anzeigen** zu können.</span><span class="sxs-lookup"><span data-stu-id="00cb2-144">Select **New** to view the **New item** panel.</span></span> 

       ![Seite "Lerninhaltsrepository" in SharePoint die Option Neu.](../media/learning/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="00cb2-146">Fügen Sie **im Bereich** Neues Element im Feld **Titel** einen Verzeichnisnamen Ihrer Wahl hinzu.</span><span class="sxs-lookup"><span data-stu-id="00cb2-146">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="00cb2-147">Fügen Sie **im Feld Ordner-URL** die URL dem Lerninhaltsordner hinzu.</span><span class="sxs-lookup"><span data-stu-id="00cb2-147">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="00cb2-148">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="00cb2-148">Select **Save**.</span></span>

       ![Neuer Elementbereich in SharePoint die Felder Titel und Ordner-URL.](../media/learning/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="00cb2-150">Die **Seite Lern-App-Inhaltsrepository** wird mit den neuen Lerninhalten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="00cb2-150">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![Seite "Lerninhaltsrepository" in SharePoint, auf der die aktualisierten Informationen angezeigt werden.](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="00cb2-152">Um einen umfassenderen Zugriff auf das Inhaltsrepository der Lern-App zu ermöglichen, wird in Kürze ein Link zur Liste in der Benutzeroberfläche von Viva Learning (Vorschau) verfügbar sein, auf der Benutzer Zugriff anfordern und letztendlich dazu beitragen können, die Liste auffüllen zu können.</span><span class="sxs-lookup"><span data-stu-id="00cb2-152">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (Preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="00cb2-153">Websitebesitzer und globale Administratoren müssen Zugriff auf die Liste gewähren.</span><span class="sxs-lookup"><span data-stu-id="00cb2-153">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="00cb2-154">Der Zugriff ist nur für die Liste spezifisch und gilt nicht für die Website, auf der die Liste gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="00cb2-154">Access is specific to the list only and does not apply to the site where the list is stored.</span></span> <span data-ttu-id="00cb2-155">Weitere Informationen finden Sie weiter unten in diesem Artikel unter [Bereitstellen](#provide-your-own-organizations-content) der Inhalte Ihrer eigenen Organisation.</span><span class="sxs-lookup"><span data-stu-id="00cb2-155">For more information, see [Provide your own organization's content](#provide-your-own-organizations-content) later in this article.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="00cb2-156">Krümmung der Ordner-URL-Dokumentbibliothek</span><span class="sxs-lookup"><span data-stu-id="00cb2-156">Folder URL document library curation</span></span>

<span data-ttu-id="00cb2-157">Standardmetadaten (z. B. geändertes Datum, erstellt durch Dokumentname, Inhaltstyp und Organisationsname) werden von der Microsoft Graph-API automatisch in Das Lernen von Viva Learning (Vorschau) gezogen.</span><span class="sxs-lookup"><span data-stu-id="00cb2-157">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (Preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="00cb2-158">Um die allgemeine Such- und Suchrelevanz des Inhalts zu verbessern, empfehlen wir das Hinzufügen einer **Beschreibungsspalte.**</span><span class="sxs-lookup"><span data-stu-id="00cb2-158">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="00cb2-159">Führen Sie **die** folgenden Schritte aus, um der Dokumentbibliotheksseite eine Beschreibungsspalte hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="00cb2-159">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="00cb2-160">Wählen Sie **auf der** Seite Dokumente die Option Spalte **hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="00cb2-160">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="00cb2-161">Wählen Sie **die Option Aktionen** anzeigen aus, und wählen Sie dann Einzelne **Textzeile aus.**</span><span class="sxs-lookup"><span data-stu-id="00cb2-161">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![Seite "Dokumente" in SharePoint zeigt die Optionen Aktionen anzeigen mit hervorgehobener Textzeile.](../media/learning/learning-sharepoint-curation1.png)

3. <span data-ttu-id="00cb2-163">Fügen Sie **im Bereich** Spalte erstellen im **Feld Name** einen beschreibenden Namen für die Spalte hinzu.</span><span class="sxs-lookup"><span data-stu-id="00cb2-163">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="00cb2-164">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="00cb2-164">Select **Save**.</span></span>

     ![Erstellen Sie einen Spaltenbereich in SharePoint, in dem der Name und andere Felder angezeigt werden.](../media/learning/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="00cb2-166">Fügen Sie **auf** der Seite Dokumente in der **Spalte Beschreibung** benutzerdefinierte Beschreibungen für jedes Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="00cb2-166">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="00cb2-167">Wenn keine Beschreibung angegeben wird, stellt Viva Learning (Vorschau) eine Standardnachricht zur Verfügung, die den Inhalt als aus Ihrer eigenen Bibliothek SharePoint hervorhebt.</span><span class="sxs-lookup"><span data-stu-id="00cb2-167">If no description is supplied, Viva Learning (Preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![Die Seite Dokumente in SharePoint die Beschreibungen in der Spalte Beschreibung.](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a><span data-ttu-id="00cb2-169">Bereitstellen der Inhalte Ihrer eigenen Organisation</span><span class="sxs-lookup"><span data-stu-id="00cb2-169">Provide your own organization's content</span></span>

<span data-ttu-id="00cb2-170">Wissensadministratoren können auf das Lern-App-Inhaltsrepository ihrer Organisation in SharePoint zugreifen, wo sie Verweise auf organisationsübergreifende Dokumentbibliotheken bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="00cb2-170">Knowledge admins can access their organization’s Learning App Content Repository in SharePoint, where they can provide references to cross-organization document libraries.</span></span> <span data-ttu-id="00cb2-171">Inhalte in diesen Bibliotheken werden dann in "Viva Learning" (Vorschau) als Lerninhalte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00cb2-171">Content within these libraries will be then surfaced as learning content in Viva Learning (Preview).</span></span>

1. <span data-ttu-id="00cb2-172">Wählen Sie in Viva Learning (Vorschau) **weitere Optionen** (**...**) aus, und wählen Sie **dann Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="00cb2-172">In Viva Learning (Preview), select **More options** (**...**), and then select **Settings**.</span></span>

     ![SharePoint Bibliotheksseite, auf der die Option Weitere Optionen und Einstellungen angezeigt wird.](../media/learning/learning-sharepoint-library-1.png)
     
2. <span data-ttu-id="00cb2-174">Wählen **Einstellungen** unter Berechtigungen **aus.**</span><span class="sxs-lookup"><span data-stu-id="00cb2-174">Under **Settings**, select **Permissions**.</span></span>

     ![Einstellungen option page in SharePoint zeigt die Berechtigungen und Zugriffsoptionen überprüfen.](../media/learning/learning-sharepoint-library-2.png)

3. <span data-ttu-id="00cb2-176">Wählen **Sie Zugriff überprüfen** aus, um eine Verbindung mit der zentralen Bibliothek Ihrer Organisation herzustellen.</span><span class="sxs-lookup"><span data-stu-id="00cb2-176">Select **Check access** to connect to your organization’s centralized library.</span></span>
     
