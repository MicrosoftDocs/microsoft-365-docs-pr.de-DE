---
title: Importieren eines Ausdruckssatzes mithilfe eines SKOS-basierten Formats
description: Informationen zum Importieren eines Ausdruckssatzes mithilfe eines SKOS-basierten Formats
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296075"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="7ca70-103">Importieren eines Ausdruckssatzes mithilfe eines SKOS-basierten Formats</span><span class="sxs-lookup"><span data-stu-id="7ca70-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="7ca70-104">Sie können einen Ausdruckssätzen mit einem SKOS-basierten Format importieren.</span><span class="sxs-lookup"><span data-stu-id="7ca70-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="7ca70-105">Ausführliche Informationen zum Format finden Sie unter [SharePoint Taxonomie SKOS Format Reference](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="7ca70-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span>

<span data-ttu-id="7ca70-106">Es wird empfohlen, ihre Importdateien auf weniger als 20.000 Begriffe zu halten.</span><span class="sxs-lookup"><span data-stu-id="7ca70-106">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="7ca70-107">Größere Dateien können die für die Überprüfung und den Import entstehende Zeit verlängern.</span><span class="sxs-lookup"><span data-stu-id="7ca70-107">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="7ca70-108">Erweitern Sie im SharePoint Admin Center die Option **Inhaltsdienste**, und klicken Sie dann auf **Terminologiespeicher**.</span><span class="sxs-lookup"><span data-stu-id="7ca70-108">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="7ca70-109">Wählen Sie die Ausdrucksgruppe aus, in die Sie den Ausdruckssätze importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7ca70-109">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="7ca70-110">Klicken Sie auf der Befehlsleiste auf **Ausdruckssätze importieren**.</span><span class="sxs-lookup"><span data-stu-id="7ca70-110">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="7ca70-111">Wenn Sie eine Beispieldatei herunterladen möchten, die als Vorlage verwendet werden soll, klicken Sie auf **Sample-Metadata. TTL** , um eine Beispieldatei abzurufen, in der das SKOS-basierte Format verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7ca70-111">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="7ca70-112">Erstellen Sie die Importdatei, die die Ausdruckssätze enthält & Begriffe, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7ca70-112">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="7ca70-113">Wählen Sie unter **Dateiformat**die Option **SKOS (\*. TTL)** aus.</span><span class="sxs-lookup"><span data-stu-id="7ca70-113">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="7ca70-114">Klicken Sie auf **Durchsuchen** , navigieren Sie zu und fügen Sie die Importdatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="7ca70-114">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="7ca70-115">Klicken Sie auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="7ca70-115">Click **Import**.</span></span> <span data-ttu-id="7ca70-116">Schließen Sie den Bereich erst, wenn der Import abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="7ca70-116">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="7ca70-117">Bei einem erfolgreichen Import der Datei wird eine Erfolgsmeldung angezeigt, und der Laufzeitspeicher wird aktualisiert, und Sie können zu den neu erstellten Ausdruckssätzen navigieren.</span><span class="sxs-lookup"><span data-stu-id="7ca70-117">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ca70-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ca70-118">See also</span></span>

[<span data-ttu-id="7ca70-119">Einführung in verwaltete Metadaten</span><span class="sxs-lookup"><span data-stu-id="7ca70-119">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="7ca70-120">Dokument Verständnis Übersicht</span><span class="sxs-lookup"><span data-stu-id="7ca70-120">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="7ca70-121">Importieren von Ausdruckssätzen (Websiteebene)</span><span class="sxs-lookup"><span data-stu-id="7ca70-121">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)