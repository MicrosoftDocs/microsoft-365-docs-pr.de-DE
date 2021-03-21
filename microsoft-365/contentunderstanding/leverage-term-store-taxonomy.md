---
title: Nutzung der Terminologiespeichertaxonomie beim Erstellen eines Extraktors
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
description: Nutzen Sie die Taxonomie von Terminologiespeicher, wenn Sie einen Extraktor in Ihrem Dokumentverständnismodell in Microsoft SharePoint Syntex erstellen.
ms.openlocfilehash: b8dfc028e0a18f3345fec466ec5e0079ed2d11ce
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925344"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="65226-103">Nutzung der Terminologiespeichertaxonomie beim Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="65226-103">Leverage term store taxonomy when creating an extractor</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

<span data-ttu-id="65226-104">Wenn Sie mit SharePoint Syntex einen Extraktor in Ihrem Dokumentverständnis-Modell erstellen, können Sie die globalen Terminologie-Gruppen im [Terminologiespeicher](/sharepoint/managed-metadata) nutzen, um bevorzugte Begriffe für die von Ihnen extrahierten Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="65226-104">When you create an extractor in your document understanding model using SharePoint Syntex, you can take advantage of global term sets in the [term store](/sharepoint/managed-metadata) to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="65226-105">Ihr Modell identifiziert und klassifiziert beispielsweise alle **Vertrags** dokumente, die in die Dokumentbibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="65226-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="65226-106">Darüber hinaus extrahiert das Modell aus jedem Vertrag einen **Vertragsdienst** wert und zeigt ihn in einer Spalte in Ihrer Bibliotheksansicht an.</span><span class="sxs-lookup"><span data-stu-id="65226-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="65226-107">Unter den verschiedenen Vertragsdienst-Werten in den Verträgen gibt es mehrere ältere Werte, die Ihr Unternehmen nicht mehr verwendet und die umbenannt wurden.</span><span class="sxs-lookup"><span data-stu-id="65226-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="65226-108">So sollten beispielsweise alle Bezüge auf die Begriffe *Design*, *Grafiken* oder *Topographie*-Vertragsdienste als *Kreativ* bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="65226-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="65226-109">Wenn Ihr Modell einen der veralteten Begriffe aus einem Vertragsdokument extrahiert, soll der aktuelle Ausdruck – Kreativ – in Ihrer Bibliotheksansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="65226-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="65226-110">Im folgenden Beispiel sehen wir beim Trainieren des Modells, dass ein Beispieldokument den veralteten Begriff *Design* enthält.</span><span class="sxs-lookup"><span data-stu-id="65226-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![Terminologiespeicher](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a><span data-ttu-id="65226-112">Verwenden Sie eine Spalte für verwaltete Metadaten in Ihrem Extraktor</span><span class="sxs-lookup"><span data-stu-id="65226-112">Use a Managed metadata column in your extractor</span></span>

<span data-ttu-id="65226-113">Ausdruckssätze werden im Terminologiespeicher für verwaltete Metadatendienste (MMS) im SharePoint Online Admin Center konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="65226-113">Term sets are configured in the Managed Metadata services (MMS) term store in the SharePoint admin center.</span></span> <span data-ttu-id="65226-114">Im folgenden Beispiel ist der [Ausdruckssatz](/sharepoint/managed-metadata#term-set) für *Vertragsdienste* so konfiguriert, dass er mehrere Begriffe enthält, einschließlich *Kreativ*.</span><span class="sxs-lookup"><span data-stu-id="65226-114">In the example below, the *Contract Services* [term set](/sharepoint/managed-metadata#term-set) is configured to include several terms, including *Creative*.</span></span>  <span data-ttu-id="65226-115">Die Details dafür zeigen, dass der Begriff drei Synonyme (*Design*, *Grafiken* und *Topographie*) aufweist, und die Synonyme sollten in *Kreativ* übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="65226-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span> 

   ![Ausdruckssatz](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="65226-117">Es kann viele Gründe geben, warum Sie möglicherweise ein Synonym in Ihrem Ausdruckssatz verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="65226-117">There could be many reasons why you might want to use a synonym in your term set.</span></span> <span data-ttu-id="65226-118">Beispielsweise kann es veraltete Ausdrücke, umbenannte Ausdrücke oder Abweichungen zwischen den Abteilungen Ihres Unternehmens bei der Benennung geben.</span><span class="sxs-lookup"><span data-stu-id="65226-118">For example, there could be outdated terms, renamed terms, or variations between your organizations departments on naming.</span></span>

<span data-ttu-id="65226-119">Damit das Feld für verwaltete Metadaten zur Auswahl steht, wenn Sie Ihren Extraktor in Ihrem Modell erstellen, müssen Sie [es als Sitespalte für verwaltete Metadaten hinzufügen](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span><span class="sxs-lookup"><span data-stu-id="65226-119">To make the managed metadata field available to select when you create your extractor in your model, you need to [add it as a managed-metadata site column](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span></span> <span data-ttu-id="65226-120">Nachdem Sie die Sitespalte hinzugefügt haben, können Sie diese auswählen, wenn Sie den Extraktor für Ihr Modell erstellen.</span><span class="sxs-lookup"><span data-stu-id="65226-120">After you add the site column, you can select it when you create the extractor for your model.</span></span>

   ![Vertragsservice](../media/content-understanding/contract-services.png)</br>


<span data-ttu-id="65226-122">Nach dem Anwenden Ihres Modells auf die Dokumentbibliothek wird beim Hochladen von Dokumenten in die Bibliothek in der Spalte *Kreative Dienste* der bevorzugte Ausdruck (*Kreativ*) angezeigt, wenn der Extraktor einen der Werte des Synonyms ermittelt (*Design*, *Grafik* und *Topographie*).</span><span class="sxs-lookup"><span data-stu-id="65226-122">After applying your model to the document library, when documents are uploaded to library, the *Creative Services* column will display the preferred term (*Creative*) when the extractor finds any of the synonym values (*Design*, *Graphics*, and *Topography*).</span></span>

   ![Vertragsdienstspalte](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a><span data-ttu-id="65226-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65226-124">See Also</span></span>
[<span data-ttu-id="65226-125">Einführung in Verwaltete Metadaten</span><span class="sxs-lookup"><span data-stu-id="65226-125">Introduction to Managed Metadata</span></span>](/sharepoint/managed-metadata#terms)

[<span data-ttu-id="65226-126">Erstellen eines Extraktors</span><span class="sxs-lookup"><span data-stu-id="65226-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="65226-127">Erstellen einer verwalteten Metadatenspalte</span><span class="sxs-lookup"><span data-stu-id="65226-127">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)