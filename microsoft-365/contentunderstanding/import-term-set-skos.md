---
title: Importieren eines Ausdruckssatzes mithilfe eines SKOS-basierten Formats
description: Erfahren Sie, wie Sie einen Ausdruckssatz mit einem SKOS-basierten Format importieren
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 96ffa22880aa9bcb70c0f7159ac7587c911b375b
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087355"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="63f90-103">Importieren eines Ausdruckssatzes mithilfe eines SKOS-basierten Formats</span><span class="sxs-lookup"><span data-stu-id="63f90-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="63f90-104">Sie können einen Ausdruckssatz mit einem SKOS-basierten Format importieren.</span><span class="sxs-lookup"><span data-stu-id="63f90-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="63f90-105">Ausführliche Informationen zum Format finden Sie unter [SharePoint-Taxonomie SKOS-Format Referenz](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="63f90-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span>

<span data-ttu-id="63f90-106">Es wird empfohlen, Ihre Importdateien auf weniger als 20.000 Ausdrücke zu belassen.</span><span class="sxs-lookup"><span data-stu-id="63f90-106">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="63f90-107">Größere Dateien können die Zeit für die Überprüfung und den Import verlängern.</span><span class="sxs-lookup"><span data-stu-id="63f90-107">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="63f90-108">Erweitern Sie im SharePoint Admin Center **Inhaltsdienste**, und klicken Sie dann auf **Terminologiespeicher**.</span><span class="sxs-lookup"><span data-stu-id="63f90-108">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="63f90-109">Wählen Sie die Ausdrucksgruppe aus, in die Sie den Ausdruckssatz importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="63f90-109">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="63f90-110">Klicken Sie auf der Befehlsleiste auf **Import Ausdruckssatz**.</span><span class="sxs-lookup"><span data-stu-id="63f90-110">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="63f90-111">Wenn Sie eine Beispieldatei herunterladen möchten, die Sie als Vorlage verwenden möchten, klicken Sie auf **sample-metadata.ttl**, um eine Beispieldatei mit dem SKOS-basierten Format abzurufen.</span><span class="sxs-lookup"><span data-stu-id="63f90-111">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="63f90-112">Erstellen Sie die Importdatei mit den Ausdruckssätze & Ausdrücke, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="63f90-112">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="63f90-113">Unter **Dateiformat**, wählen Sie **SKOS (\*.ttl)** aus.</span><span class="sxs-lookup"><span data-stu-id="63f90-113">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="63f90-114">Klicken Sie auf **Durchsuchen**, navigieren Sie zu Ihrer Importdatei, und fügen Sie sie hinzu.</span><span class="sxs-lookup"><span data-stu-id="63f90-114">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="63f90-115">Klicken Sie auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="63f90-115">Click **Import**.</span></span> <span data-ttu-id="63f90-116">Schließen Sie den Bereich erst, wenn der Import abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="63f90-116">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="63f90-117">Bei einem erfolgreichen Import der Datei wird eine Erfolgsmeldung angezeigt, und der Terminologiespeicher wird aktualisiert, und Sie können zu den neu erstellten Ausdruckssätzen wechseln.</span><span class="sxs-lookup"><span data-stu-id="63f90-117">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="63f90-118">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="63f90-118">See also</span></span>

[<span data-ttu-id="63f90-119">Einführung in verwaltete Metadaten</span><span class="sxs-lookup"><span data-stu-id="63f90-119">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="63f90-120">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="63f90-120">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="63f90-121">Importieren von Ausdruckssatz (Websiteebene)</span><span class="sxs-lookup"><span data-stu-id="63f90-121">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)