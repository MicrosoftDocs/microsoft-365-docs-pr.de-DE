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
description: Wenn einem Advanced eDiscovery-Fall ein Verwahrer hinzugefügt wird, werden alle Inhalte, die als teilweise indiziert betrachtet wurden, erneut verarbeitet, um sie vollständig durchsuchbar zu machen.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911209"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="e651e-103">Erweiterte Indizierung der Daten von Verwaltungsberechtigten</span><span class="sxs-lookup"><span data-stu-id="e651e-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="e651e-104">Wenn einem Advanced eDiscovery-Fall ein Verwahrer hinzugefügt wird, werden alle Inhalte, die als teilweise indiziert betrachtet wurden, erneut verarbeitet, um sie vollständig durchsuchbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="e651e-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="e651e-105">Dieser Prozess wird als *Erweiterte Indizierung bezeichnet.*</span><span class="sxs-lookup"><span data-stu-id="e651e-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="e651e-106">Inhalte können aus einer Reihe von Gründen teilweise indiziert werden, z. B. aus dem Vorhandensein von Bildern, nicht unterstützten Dateitypen oder beim Indizierung von Dateigrößenbeschränkungen.</span><span class="sxs-lookup"><span data-stu-id="e651e-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="e651e-107">Weitere Informationen zur Verarbeitung von Support und teilweise indizierten Elementen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="e651e-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="e651e-108">Unterstützte Dateitypen in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="e651e-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="e651e-109">Teilweise indizierte Elemente in der Inhaltssuche in Office 365</span><span class="sxs-lookup"><span data-stu-id="e651e-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="e651e-110">Von der Exchange-Suche indizierte Dateiformate</span><span class="sxs-lookup"><span data-stu-id="e651e-110">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="e651e-111">Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="e651e-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="e651e-112">Anzeigen erweiterter Indizierungsergebnisse</span><span class="sxs-lookup"><span data-stu-id="e651e-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="e651e-113">Nachdem der Erweiterte Indizierungsprozess abgeschlossen ist, können Sie sich ein Verständnis der Effektivität der Neuverarbeitung machen.</span><span class="sxs-lookup"><span data-stu-id="e651e-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="e651e-114">In der Ansicht Erweiterte Indizierungsergebnisse auf der Registerkarte **Verarbeitung** für einen Fall listet das Diagramm die Anzahl der Elemente auf, die dem *Hybridindex hinzugefügt wurden.*</span><span class="sxs-lookup"><span data-stu-id="e651e-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="e651e-115">Im Hybridindex speichert Advanced eDiscovery den erneut verarbeiteten Inhalt.</span><span class="sxs-lookup"><span data-stu-id="e651e-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="e651e-116">Diese Ansicht enthält auch die Anzahl der Elemente, die eine Korrektur erfordern, und ein weiteres Diagramm mit Fehlern nach Dateityp.</span><span class="sxs-lookup"><span data-stu-id="e651e-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="e651e-117">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="e651e-117">For more information, see:</span></span>

- [<span data-ttu-id="e651e-118">Beheben von Fehlern beim Verarbeiten von Daten</span><span class="sxs-lookup"><span data-stu-id="e651e-118">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="e651e-119">Korrektur von Fehlern einzelner Elemente</span><span class="sxs-lookup"><span data-stu-id="e651e-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="e651e-120">Aktualisieren des erweiterten Indexes für Verwahrer</span><span class="sxs-lookup"><span data-stu-id="e651e-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="e651e-121">Wenn einem Advanced eDiscovery-Fall ein Verwahrer hinzugefügt wird, werden alle teilweise indizierten Elemente erneut verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="e651e-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="e651e-122">Im Weiteren können jedoch dem Postfach oder #A0 eines Benutzers teilweise indizierte Elemente hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e651e-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="e651e-123">Bei Bedarf können Sie den Index für bestimmte Verwahrer aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e651e-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="e651e-124">Weitere Informationen finden Sie [unter Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span><span class="sxs-lookup"><span data-stu-id="e651e-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="e651e-125">Sie können den Index auch für alle Custodians in einem Fall aktualisieren, indem Sie auf der Registerkarte Verarbeitung auf den **Index** Aktualisieren **klicken.**</span><span class="sxs-lookup"><span data-stu-id="e651e-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="e651e-126">Das Aktualisieren von Indizes für Custodian ist ein langer Prozess.</span><span class="sxs-lookup"><span data-stu-id="e651e-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="e651e-127">Es wird empfohlen, Indizes in einem Fall nicht mehr als einmal täglich zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e651e-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>