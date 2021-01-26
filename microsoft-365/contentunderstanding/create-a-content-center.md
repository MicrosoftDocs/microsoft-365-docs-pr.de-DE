---
title: Erstellen eines inhaltscenters in Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Erhalten Sie Informationen zum Erstellen eines Inhaltscenters.
ms.openlocfilehash: 4377cbfbda8572fe9e08a079a05146961105298b
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976531"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="a7c33-103">Erstellen eines inhaltscenters in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="a7c33-103">Create a content center in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="a7c33-104">Zum Erstellen und Verwalten von Dokumentverständnismodellen benötigen Sie zuerst ein Inhaltscenter.</span><span class="sxs-lookup"><span data-stu-id="a7c33-104">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="a7c33-105">Beim Inhaltscenter handelt es sich um die Modellerstellungsoberfläche. Es enthält aber auch Informationen dazu, auf welche Dokumentbibliotheken veröffentlichte Modelle angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="a7c33-105">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![Auswählen einer Dokumentbibliothek](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="a7c33-107">Sie erstellen ein Standardinhaltscenter während des [Setups](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="a7c33-107">You create a default content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="a7c33-108">Ein SharePoint-Administrator kann aber bei Bedarf auch zusätzliche Center erstellen.</span><span class="sxs-lookup"><span data-stu-id="a7c33-108">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="a7c33-109">Während ein einzelnes Inhaltscenter für Umgebungen, für die Sie eine Rollup aller Modellaktivitäten durchführen möchten, möglicherweise in Ordnung ist, möchten Sie möglicherweise zusätzliche Zentren für mehrere Abteilungen in Ihrer Organisation einrichten, die möglicherweise unterschiedliche Bedürfnisse und Berechtigungsanforderungen an Ihre Modelle haben.</span><span class="sxs-lookup"><span data-stu-id="a7c33-109">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and permission requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="a7c33-110">Ein SharePoint-Administrator kann eine Inhaltscenter-Website erstellen, wie er auch eine beliebige andere [SharePoint-Website](https://docs.microsoft.com/sharepoint/create-site-collection) über den Bereitstellungsbereich der Admin Center-Website erstellen würde.</span><span class="sxs-lookup"><span data-stu-id="a7c33-110">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) through the admin center site provisioning panel.</span></span>

<span data-ttu-id="a7c33-111">So erstellen Sie ein neues Inhaltscenter:</span><span class="sxs-lookup"><span data-stu-id="a7c33-111">To create a new content center:</span></span>

1. <span data-ttu-id="a7c33-112">Wechseln Sie im Microsoft 365 Admin Center zum SharePoint Admin Center.</span><span class="sxs-lookup"><span data-stu-id="a7c33-112">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="a7c33-113">Wählen Sie im SharePoint Admin Center unter **Websites** die Option **Aktive Websites** aus.</span><span class="sxs-lookup"><span data-stu-id="a7c33-113">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="a7c33-114">Klicken Sie auf der Seite **Aktive Websites** auf **Erstellen**, und wählen Sie dann **Sonstige Optionen** aus.</span><span class="sxs-lookup"><span data-stu-id="a7c33-114">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="a7c33-115">Wählen Sie im Menü **Vorlage auswählen** die Option **Inhaltscenter** aus.</span><span class="sxs-lookup"><span data-stu-id="a7c33-115">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="a7c33-116">Stellen Sie für die neue Website Angaben für **Websitename**, **Primärer Administrator** und **Sprache** bereit.</span><span class="sxs-lookup"><span data-stu-id="a7c33-116">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="a7c33-117">Sie können eine inhaltscenter-Website für die Darstellung in einer der verfügbaren Sprachen auswählen. Beachten Sie jedoch, dass zurzeit nur für englische Dateien Modelle erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="a7c33-117">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span> <span data-ttu-id="a7c33-118">Beachten Sie auch, dass die Standardsprache der Website nach der Erstellung (wie bei anderen Websitevorlagen) nicht mehr bearbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a7c33-118">Also note that like other site templates, the default site language isn't editable after the site is created.</span></span></br>

6. <span data-ttu-id="a7c33-119">Wählen Sie **Fertigstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="a7c33-119">Select **Finished**.</span></span>
 
<span data-ttu-id="a7c33-120">Nachdem Sie eine Inhaltscenter-Website erstellt haben, wird Sie im SharePoint Admin Center auf der Seite **Aktive Websites** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a7c33-120">After you create a content center site, you will see it listed on the **Active sites** page in the SharePoint admin center.</span></span> 

### <a name="give-access-to-additional-users"></a><span data-ttu-id="a7c33-121">Gewähren des Zugriffs für zusätzliche Benutzer</span><span class="sxs-lookup"><span data-stu-id="a7c33-121">Give access to additional users</span></span>
 
<span data-ttu-id="a7c33-122">Nachdem Sie die Website erstellt haben, können Sie zusätzlichen Benutzern den Zugriff auf die Website über das standardmäßige [SharePoint-Websiteberechtigungsmodell](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions) gewähren.</span><span class="sxs-lookup"><span data-stu-id="a7c33-122">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="a7c33-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7c33-123">See Also</span></span>
[<span data-ttu-id="a7c33-124">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="a7c33-124">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="a7c33-125">Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="a7c33-125">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="a7c33-126">Erstellen eines Inhaltscenters</span><span class="sxs-lookup"><span data-stu-id="a7c33-126">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="a7c33-127">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="a7c33-127">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="a7c33-128">Erstellen eines Formularverarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="a7c33-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="a7c33-129">Anwenden eines Modells</span><span class="sxs-lookup"><span data-stu-id="a7c33-129">Apply a model</span></span>](apply-a-model.md)    
