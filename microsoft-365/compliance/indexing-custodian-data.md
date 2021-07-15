---
title: Erweiterte Indizierung der Daten von Verwaltungsberechtigten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Wenn ein Verwahrer zu einem Advanced eDiscovery Fall hinzugefügt wird, werden alle Inhalte, die als teilweise indiziert eingestuft wurden, erneut verarbeitet, um sie vollständig durchsuchbar zu machen.
ms.openlocfilehash: 34855eb168dd10fc500e2e57fe1d57ad81449452
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437976"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="a98e4-103">Erweiterte Indizierung der Daten von Verwaltungsberechtigten</span><span class="sxs-lookup"><span data-stu-id="a98e4-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="a98e4-104">Wenn ein Verwahrer zu einem Advanced eDiscovery Fall hinzugefügt wird, werden alle Inhalte, die als teilweise indiziert betrachtet wurden oder mit denen Indizierungsfehler aufgetreten sind, neu indiziert, um sie vollständig durchsuchbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="a98e4-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed or had indexing errors with is reindexed to make it fully searchable.</span></span>  <span data-ttu-id="a98e4-105">Dieser Neuindizierungsprozess wird als *erweiterte Indizierung* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a98e4-105">This reindexing process is called *Advanced indexing*.</span></span> <span data-ttu-id="a98e4-106">Es gibt eine Reihe von Gründen, warum Inhalte teilweise indiziert werden oder Indizierungsfehler aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a98e4-106">There are a number of reasons that content is partially indexed or has indexing errors.</span></span> <span data-ttu-id="a98e4-107">Dazu gehören Bilddateien oder das Vorhandensein von Bildern in einer Datei, nicht unterstützte Dateitypen oder Indizierungsgrenzwerte für die Dateigröße.</span><span class="sxs-lookup"><span data-stu-id="a98e4-107">This includes image files or the presence of images in a file, unsupported file types, or file sized indexing limits.</span></span> <span data-ttu-id="a98e4-108">Bei SharePoint Dateien wird die erweiterte Indizierung nur für Elemente ausgeführt, die als teilweise indiziert gekennzeichnet sind oder die Indizierungsfehler aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a98e4-108">For SharePoint files, Advanced indexing only runs on items are marked as partially indexed or that have indexing errors.</span></span> <span data-ttu-id="a98e4-109">In Exchange werden E-Mail-Nachrichten mit Bildanlagen nicht als teilweise indiziert oder mit Indizierungsfehlern gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="a98e4-109">In Exchange, email messages that have image attachments are not marked as partially indexed or with indexing errors.</span></span> <span data-ttu-id="a98e4-110">Dies bedeutet, dass diese Dateien nicht vom erweiterten Indizierungsprozess neu indiziert werden.</span><span class="sxs-lookup"><span data-stu-id="a98e4-110">This means that those files will not be reindexed by the Advanced indexing process.</span></span>

<span data-ttu-id="a98e4-111">Weitere Informationen zur Verarbeitungsunterstützung und teilweise indizierten Elementen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="a98e4-111">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="a98e4-112">Unterstützte Dateitypen in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a98e4-112">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="a98e4-113">Teilweise indizierte Elemente in der Inhaltssuche in Office 365</span><span class="sxs-lookup"><span data-stu-id="a98e4-113">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="a98e4-114">Von der Exchange-Suche indizierte Dateiformate</span><span class="sxs-lookup"><span data-stu-id="a98e4-114">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="a98e4-115">Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="a98e4-115">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="a98e4-116">Anzeigen erweiterter Indizierungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="a98e4-116">Viewing Advanced indexing results</span></span>

<span data-ttu-id="a98e4-117">Nachdem der Prozess der erweiterten Indizierung abgeschlossen ist, können Sie die Effektivität der Erneutverarbeitung verstehen.</span><span class="sxs-lookup"><span data-stu-id="a98e4-117">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="a98e4-118">In der Ansicht "Erweiterte Indizierungsergebnisse" auf der Registerkarte **"Verarbeitung"** für einen Fall listet das Diagramm die Anzahl der Elemente auf, die dem *Hybridindex* hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="a98e4-118">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="a98e4-119">Im Hybridindex speichert Advanced eDiscovery den erneut verarbeiteten Inhalt.</span><span class="sxs-lookup"><span data-stu-id="a98e4-119">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="a98e4-120">Diese Ansicht enthält auch die Anzahl der Elemente, die eine Korrektur erfordern, und ein weiteres Diagramm von Fehlern nach Dateityp.</span><span class="sxs-lookup"><span data-stu-id="a98e4-120">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="a98e4-121">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="a98e4-121">For more information, see:</span></span>

- [<span data-ttu-id="a98e4-122">Beheben von Fehlern beim Verarbeiten von Daten</span><span class="sxs-lookup"><span data-stu-id="a98e4-122">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="a98e4-123">Korrektur von Fehlern einzelner Elemente</span><span class="sxs-lookup"><span data-stu-id="a98e4-123">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="a98e4-124">Aktualisieren des erweiterten Index für Verwahrer</span><span class="sxs-lookup"><span data-stu-id="a98e4-124">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="a98e4-125">Wenn ein Verwahrer zu einem Advanced eDiscovery Fall hinzugefügt wird, werden alle teilweise indizierten Elemente erneut verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a98e4-125">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="a98e4-126">Wenn die Zeit vergeht, können jedoch mehr teilweise indizierte Elemente zum Postfach oder OneDrive Konto eines Benutzers hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a98e4-126">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="a98e4-127">Bei Bedarf können Sie den Index für einen bestimmten Verwahrer aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a98e4-127">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="a98e4-128">Weitere Informationen finden Sie unter [Verwalten von Verwaltern in einem Advanced eDiscovery Fall.](manage-new-custodians.md#re-index-custodian-data)</span><span class="sxs-lookup"><span data-stu-id="a98e4-128">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="a98e4-129">Sie können den Index für alle Verwahrer in einem Fall auch aktualisieren, indem Sie auf der Registerkarte **"Verarbeitung"** auf den **Index aktualisieren** klicken.</span><span class="sxs-lookup"><span data-stu-id="a98e4-129">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="a98e4-130">Das Aktualisieren von Verwahrungsindizes ist ein langer Prozess.</span><span class="sxs-lookup"><span data-stu-id="a98e4-130">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="a98e4-131">Es wird empfohlen, indizes nicht mehr als einmal pro Tag in einem Fall zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a98e4-131">It's recommended that you don't update indexes more than once a day in a case.</span></span>
