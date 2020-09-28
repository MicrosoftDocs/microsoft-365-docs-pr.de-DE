---
title: Erstellen eines inhaltscenters in Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Hier erfahren Sie, wie Sie ein inhaltscenter erstellen.
ms.openlocfilehash: 62977bc5a34b041e9e958ff46e0dbc010d6bd822
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295432"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="52114-103">Erstellen eines inhaltscenters in Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="52114-103">Create a content center in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="52114-104">Der Inhalt in diesem Artikel ist für die Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="52114-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="52114-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="52114-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="52114-106">Zum Erstellen und Verwalten von Dokument Verständnis Modellen benötigen Sie zunächst ein inhaltscenter.</span><span class="sxs-lookup"><span data-stu-id="52114-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="52114-107">Das inhaltscenter ist die Modell Erstellungs Schnittstelle und enthält außerdem Informationen darüber, auf welche Dokumentbibliotheken veröffentlichte Modelle angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="52114-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![Auswählen einer doc-Bibliothek](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="52114-109">Sie erstellen ein anfängliches inhaltscenter während des [Setups](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="52114-109">You create an initial content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="52114-110">Ein SharePoint-Administrator kann aber auch zusätzliche Center bei Bedarf erstellen.</span><span class="sxs-lookup"><span data-stu-id="52114-110">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="52114-111">Während ein einzelnes inhaltscenter für Umgebungen geeignet ist, für die Sie eine Rollup aller Modell Aktivitäten durchführen möchten, können Sie zusätzliche Center für mehrere Abteilungen in Ihrer Organisation benötigen, die unterschiedliche Anforderungen und Anforderungen für Ihre Modelle haben können.</span><span class="sxs-lookup"><span data-stu-id="52114-111">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="52114-112">Ein SharePoint-Administrator kann eine inhaltscenter-Website erstellen, wie Sie eine [beliebige andere SharePoint-Website](https://docs.microsoft.com/sharepoint/create-site-collection) mithilfe einer Websitevorlage erstellen würde.</span><span class="sxs-lookup"><span data-stu-id="52114-112">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) by using a site template.</span></span>

<span data-ttu-id="52114-113">So erstellen Sie ein neues inhaltscenter:</span><span class="sxs-lookup"><span data-stu-id="52114-113">To create a new content center:</span></span>

1. <span data-ttu-id="52114-114">Wechseln Sie im Microsoft 365 Admin Center zum SharePoint Admin Center.</span><span class="sxs-lookup"><span data-stu-id="52114-114">From the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="52114-115">Wählen Sie im SharePoint Admin Center unter **Websites**die Option **aktive Websites**aus.</span><span class="sxs-lookup"><span data-stu-id="52114-115">In the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="52114-116">Klicken Sie auf der Seite **aktive Websites** auf **Erstellen**, und wählen Sie dann **andere Optionen**aus.</span><span class="sxs-lookup"><span data-stu-id="52114-116">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="52114-117">Wählen Sie im Menü **Vorlage auswählen** die Option **Inhalts Center**aus.</span><span class="sxs-lookup"><span data-stu-id="52114-117">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="52114-118">Geben Sie für die neue Website einen **Websitenamen**, einen **primären Administrator**und eine **Sprache**an.</span><span class="sxs-lookup"><span data-stu-id="52114-118">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="52114-119">Optional können Sie eine inhaltscenter-Website auswählen, die in einer der verfügbaren Sprachen gerendert werden soll.</span><span class="sxs-lookup"><span data-stu-id="52114-119">You can optionally select a content center site to render in any of the available languages.</span></span> <span data-ttu-id="52114-120">Für englische Dateien können nur aktuelle Modelle erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="52114-120">Only current models can be created for English files.</span></span></br>

6. <span data-ttu-id="52114-121">Wählen Sie **Fertig**aus.</span><span class="sxs-lookup"><span data-stu-id="52114-121">Select **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="52114-122">Zugriff auf zusätzliche Benutzer gewähren</span><span class="sxs-lookup"><span data-stu-id="52114-122">Give access to additional users</span></span>
 
<span data-ttu-id="52114-123">Nachdem Sie die Website erstellt haben, können Sie über das standardmäßige [SharePoint-Website Berechtigungsmodell](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)weiteren Benutzern Zugriff auf die Website gewähren.</span><span class="sxs-lookup"><span data-stu-id="52114-123">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="52114-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52114-124">See Also</span></span>
[<span data-ttu-id="52114-125">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="52114-125">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="52114-126">Erstellen eines Extraktions Moduls</span><span class="sxs-lookup"><span data-stu-id="52114-126">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="52114-127">[Erstellen eines inhaltscenters](create-a-content-center.md) 
 [Dokument Verständnis Übersicht](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="52114-127">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="52114-128">Erstellen eines Formular Verarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="52114-128">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="52114-129">Anwenden eines Modells</span><span class="sxs-lookup"><span data-stu-id="52114-129">Apply a model</span></span>](apply-a-model.md)    
