---
title: Terminologiespeicher-Taxonomie beim Erstellen eines Extraktors nutzen
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Nutzen Sie die Terminologiespeicher-Taxonomie beim Erstellen eines Extraktors in Ihrem Dokument Understanding Model in Microsoft SharePoint Syntex.
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295860"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="d48bf-103">Terminologiespeicher-Taxonomie beim Erstellen eines Extraktors nutzen</span><span class="sxs-lookup"><span data-stu-id="d48bf-103">Leverage term store taxonomy when creating an extractor</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="d48bf-104">Wenn Sie einen Extraktor in Ihrem Dokument Understanding Model in SharePoint Syntex erstellen, können Sie die Terminologiespeicher-Taxonomie für [verwaltete](https://docs.microsoft.com/sharepoint/managed-metadata#terms) Metadatendienst nutzen, um bevorzugte Ausdrücke für extrahierte Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d48bf-104">When you create an extractor in your document understanding model in SharePoint Syntex, you can take advantage of [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) term store taxonomy to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="d48bf-105">Beispielsweise identifiziert und klassifiziert Ihr Modell alle **Vertrags** Dokumente, die in die Dokumentbibliothek hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="d48bf-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="d48bf-106">Darüber hinaus extrahiert das Modell auch einen **Vertrags Dienst** Wert aus jedem Vertrag und zeigt ihn in einer Spalte in der Bibliotheksansicht an.</span><span class="sxs-lookup"><span data-stu-id="d48bf-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="d48bf-107">Unter den verschiedenen Contract Services-Werten in den Verträgen gibt es mehrere ältere Werte, die Ihr Unternehmen nicht mehr verwendet und umbenannt wurde.</span><span class="sxs-lookup"><span data-stu-id="d48bf-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="d48bf-108">Beispielsweise sollten alle Verweise auf die Begriffe *Design*, *Grafiken*oder *Topographie* -Vertrags Dienste nun als *Creative*bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="d48bf-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="d48bf-109">Wenn Ihr Modell einen der veralteten Begriffe aus einem Vertragsdokument extrahiert, soll der aktuelle Ausdruck-Creative in ihrer Bibliotheksansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d48bf-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="d48bf-110">Im folgenden Beispiel sehen wir beim Training des Modells, dass ein Beispieldokument den veralteten Ausdruck von *Design*enthält.</span><span class="sxs-lookup"><span data-stu-id="d48bf-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![Terminologiespeicher](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a><span data-ttu-id="d48bf-112">Synonyme für Ausdruckssätze</span><span class="sxs-lookup"><span data-stu-id="d48bf-112">Term set synonyms</span></span> 

<span data-ttu-id="d48bf-113">Ausdruckssätze werden im SharePoint Admin Center im Terminologiespeicher für verwaltete Metadatendienst konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="d48bf-113">Term sets are configured in the Managed Metadata services term store in the SharePoint admin center.</span></span> <span data-ttu-id="d48bf-114">Im folgenden Beispiel ist der [Ausdruckssätze](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) *Contract Services* so konfiguriert, dass er eine Reihe von Begriffen enthält, einschließlich *Creative*.</span><span class="sxs-lookup"><span data-stu-id="d48bf-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="d48bf-115">Die Details dafür zeigen, dass der Ausdruck drei Synonyme enthält (*Design*, *Grafiken*und *Topographie*), und die Synonyme sollten in *Creative*übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="d48bf-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span>

   ![Ausdruckssatz](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="d48bf-117"><Mike, hier bin ich unsicher, wie ich dies beschreiben kann.</span><span class="sxs-lookup"><span data-stu-id="d48bf-117"><Mike, here is where I am unsure about how to describe this.</span></span>  <span data-ttu-id="d48bf-118">Welche Aktion weist das Modell darauf hin, dass beim Erstellen eines Extraktors zum Extrahieren und Anzeigen einer Vertrags Dienst Spalte die Spalte "markiert" ist, um den Ausdruckssätze für verwaltete Metadaten für Creative Services zu verwenden? ></span><span class="sxs-lookup"><span data-stu-id="d48bf-118">What action tells the model that when I create an extractor to extract and display a Contract Services column, how is that column "marked" to use the managed metadata term set for Creative Services?></span></span>

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a><span data-ttu-id="d48bf-119">Konfigurieren der Website Spalte für die Dokumentbibliothek für ein verwaltetes Metadatenfeld</span><span class="sxs-lookup"><span data-stu-id="d48bf-119">Configure your document library site column for a managed metadata field</span></span>


   ![Erstellen verwalteter Metadaten](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a><span data-ttu-id="d48bf-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d48bf-121">See Also</span></span>
[<span data-ttu-id="d48bf-122">Einführung in verwaltete Metadaten</span><span class="sxs-lookup"><span data-stu-id="d48bf-122">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[<span data-ttu-id="d48bf-123">Erstellen eines Extraktions Moduls</span><span class="sxs-lookup"><span data-stu-id="d48bf-123">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="d48bf-124">Erstellen einer Spalte mit verwalteten Metadaten</span><span class="sxs-lookup"><span data-stu-id="d48bf-124">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





