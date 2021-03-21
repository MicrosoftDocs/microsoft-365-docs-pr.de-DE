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
ms.openlocfilehash: 734edbb462193291b6bd2fb4a8e6afc3a0b709cb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928248"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="51c57-103">Importieren eines Ausdruckssatzes mithilfe eines SKOS-basierten Formats</span><span class="sxs-lookup"><span data-stu-id="51c57-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="51c57-104">Sie können einen Ausdruckssatz mit einem SKOS-basierten Format importieren.</span><span class="sxs-lookup"><span data-stu-id="51c57-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="51c57-105">Ausführliche Informationen zum Format finden Sie unter [SharePoint-Taxonomie SKOS-Format Referenz](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="51c57-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span> <span data-ttu-id="51c57-106">Dieses Feature benötigt eine [SharePoint Syntex](index.md)-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="51c57-106">This feature requires a [SharePoint Syntex](index.md) license.</span></span>

<span data-ttu-id="51c57-107">Es wird empfohlen, Ihre Importdateien auf weniger als 20.000 Ausdrücke zu belassen.</span><span class="sxs-lookup"><span data-stu-id="51c57-107">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="51c57-108">Größere Dateien können die Zeit für die Überprüfung und den Import verlängern.</span><span class="sxs-lookup"><span data-stu-id="51c57-108">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="51c57-109">Erweitern Sie im SharePoint Admin Center **Inhaltsdienste**, und klicken Sie dann auf **Terminologiespeicher**.</span><span class="sxs-lookup"><span data-stu-id="51c57-109">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="51c57-110">Wählen Sie die Ausdrucksgruppe aus, in die Sie den Ausdruckssatz importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="51c57-110">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="51c57-111">Klicken Sie auf der Befehlsleiste auf **Import Ausdruckssatz**.</span><span class="sxs-lookup"><span data-stu-id="51c57-111">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="51c57-112">Wenn Sie eine Beispieldatei herunterladen möchten, die Sie als Vorlage verwenden möchten, klicken Sie auf **sample-metadata.ttl**, um eine Beispieldatei mit dem SKOS-basierten Format abzurufen.</span><span class="sxs-lookup"><span data-stu-id="51c57-112">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="51c57-113">Erstellen Sie die Importdatei mit den Ausdruckssätze & Ausdrücke, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="51c57-113">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="51c57-114">Unter **Dateiformat**, wählen Sie **SKOS (\*.ttl)** aus.</span><span class="sxs-lookup"><span data-stu-id="51c57-114">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="51c57-115">Klicken Sie auf **Durchsuchen**, navigieren Sie zu Ihrer Importdatei, und fügen Sie sie hinzu.</span><span class="sxs-lookup"><span data-stu-id="51c57-115">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="51c57-116">Klicken Sie auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="51c57-116">Click **Import**.</span></span> <span data-ttu-id="51c57-117">Schließen Sie den Bereich erst, wenn der Import abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="51c57-117">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="51c57-118">Bei einem erfolgreichen Import der Datei wird eine Erfolgsmeldung angezeigt, und der Terminologiespeicher wird aktualisiert, und Sie können zu den neu erstellten Ausdruckssätzen wechseln.</span><span class="sxs-lookup"><span data-stu-id="51c57-118">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="51c57-119">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="51c57-119">See also</span></span>

[<span data-ttu-id="51c57-120">Einführung in verwaltete Metadaten</span><span class="sxs-lookup"><span data-stu-id="51c57-120">Introduction to managed metadata</span></span>](/sharepoint/managed-metadata)

[<span data-ttu-id="51c57-121">Übersicht über das Dokumentenverständnis</span><span class="sxs-lookup"><span data-stu-id="51c57-121">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="51c57-122">Importieren von Ausdruckssatz (Websiteebene)</span><span class="sxs-lookup"><span data-stu-id="51c57-122">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)