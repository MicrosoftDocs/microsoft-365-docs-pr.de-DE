---
title: Erstellen eines inhaltscenters (Vorschau)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Hier erfahren Sie, wie Sie ein inhaltscenter erstellen.
ms.openlocfilehash: 5332ffa195519aebd5ae8dd2c26d7d62fd9b3267
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612750"
---
# <a name="create-a-content-center-preview"></a><span data-ttu-id="9735a-103">Erstellen eines inhaltscenters (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="9735a-103">Create a content center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="9735a-104">Der Inhalt dieses Artikels ist für Project Cortex private Preview.</span><span class="sxs-lookup"><span data-stu-id="9735a-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="9735a-105">[Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="9735a-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="9735a-106">Zum Erstellen und Verwalten von Dokument Verständnis Modellen benötigen Sie zunächst ein inhaltscenter.</span><span class="sxs-lookup"><span data-stu-id="9735a-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="9735a-107">Das inhaltscenter ist die Schnittstelle zur Modellerstellung und enthält außerdem Informationen darüber, welche Dokumentbibliotheken auf die veröffentlichten Modelle angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="9735a-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied.</span></span></br>

   ![Auswählen einer doc-Bibliothek](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="9735a-109">Während des [Setups](set-up-content-understanding.md)wird ein anfängliches inhaltscenter erstellt, aber ein SharePoint-Administrator kann weitere nach Bedarf erstellen.</span><span class="sxs-lookup"><span data-stu-id="9735a-109">An initial content center is created during [setup](set-up-content-understanding.md), but a SharePoint admin can choose to create additional ones as needed.</span></span> <span data-ttu-id="9735a-110">Während ein einzelnes inhaltscenter für Umgebungen geeignet ist, in denen Sie eine Rollup aller Modell Aktivitäten sehen möchten, können Sie zusätzliche haben, wenn Ihr Unternehmen über mehrere Abteilungen verfügt, die unterschiedliche Anforderungen und Anforderungen für Ihre Modelle haben können.</span><span class="sxs-lookup"><span data-stu-id="9735a-110">While a single content center may be fine for environments in which you want to see a roll-up of all model activity, you may want to have additional ones if your have multiple departments within your organization that may have different needs and requirements for their models.</span></span>

<span data-ttu-id="9735a-111">Ein SharePoint-Administrator kann eine inhaltscenter-Website erstellen, wie Sie eine [beliebige andere SharePoint-Website erstellt](https://docs.microsoft.com/sharepoint/create-site-collection) – über eine Websitevorlage.</span><span class="sxs-lookup"><span data-stu-id="9735a-111">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) - through a site template.</span></span>

<span data-ttu-id="9735a-112">So erstellen Sie ein neues inhaltscenter:</span><span class="sxs-lookup"><span data-stu-id="9735a-112">To create a new content center:</span></span>

1. <span data-ttu-id="9735a-113">Wechseln Sie im Microsoft 365 Admin Center zum SharePoint Admin Center.</span><span class="sxs-lookup"><span data-stu-id="9735a-113">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="9735a-114">Wählen Sie im SharePoint Admin Center unter **Websites**die Option **aktive Websites**aus.</span><span class="sxs-lookup"><span data-stu-id="9735a-114">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="9735a-115">Klicken Sie auf der Seite **aktive Websites** auf **Erstellen**, und wählen Sie dann **andere Optionen**aus.</span><span class="sxs-lookup"><span data-stu-id="9735a-115">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="9735a-116">Wählen Sie im Menü **Vorlage auswählen** die Option **Inhalts Center**aus.</span><span class="sxs-lookup"><span data-stu-id="9735a-116">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="9735a-117">Geben Sie für die neue Website einen **Websitenamen**, einen **primären Administrator**und eine **Sprache**an.</span><span class="sxs-lookup"><span data-stu-id="9735a-117">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!Note] 
> <span data-ttu-id="9735a-118">Sie können eine inhaltscenter-Website auswählen, die in einer der verfügbaren Sprachen gerendert werden soll, beachten Sie jedoch, dass derzeit Modelle nur für englische Dateien erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="9735a-118">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span></br>

6. <span data-ttu-id="9735a-119">Klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="9735a-119">Click **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="9735a-120">Zugriff auf zusätzliche Benutzer gewähren</span><span class="sxs-lookup"><span data-stu-id="9735a-120">Give access to additional users</span></span>
 
<span data-ttu-id="9735a-121">Nachdem die Website erstellt wurde, können Sie zusätzliche Benutzer über das standardmäßige [SharePoint-Website Berechtigungsmodell](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)Zugriff auf die Website gewähren.</span><span class="sxs-lookup"><span data-stu-id="9735a-121">After the site is created, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>





## <a name="see-also"></a><span data-ttu-id="9735a-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9735a-122">See Also</span></span>
[<span data-ttu-id="9735a-123">Erstellen einer Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="9735a-123">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="9735a-124">Erstellen eines Extraktions Moduls</span><span class="sxs-lookup"><span data-stu-id="9735a-124">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="9735a-125">[Erstellen eines inhaltscenters](create-a-content-center.md) 
 [Dokument Verständnis Übersicht](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9735a-125">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="9735a-126">Erstellen eines Formular Verarbeitungsmodells</span><span class="sxs-lookup"><span data-stu-id="9735a-126">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="9735a-127">Anwenden eines Modells</span><span class="sxs-lookup"><span data-stu-id="9735a-127">Apply a model</span></span>](apply-a-model.md)    




