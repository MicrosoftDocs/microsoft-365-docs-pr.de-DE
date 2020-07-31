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
description: Wenn eine Depotbank einem erweiterten eDiscovery-Fall hinzugefügt wird, werden alle Inhalte, die als teilweise indiziert betrachtet wurden, erneut verarbeitet, damit Sie vollständig durchsuchbar sind.
ms.openlocfilehash: 95e087884b65628565e596dc8ae9f33aadc4cd9f
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527555"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="a9ed6-103">Erweiterte Indizierung der Daten von Verwaltungsberechtigten</span><span class="sxs-lookup"><span data-stu-id="a9ed6-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="a9ed6-104">Wenn eine Depotbank einem erweiterten eDiscovery-Fall hinzugefügt wird, werden alle Inhalte, die als teilweise indiziert betrachtet wurden, erneut verarbeitet, damit Sie vollständig durchsuchbar sind.</span><span class="sxs-lookup"><span data-stu-id="a9ed6-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="a9ed6-105">Dieser Vorgang wird als *Erweiterte Indizierung*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a9ed6-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="a9ed6-106">Inhalt kann teilweise aus einer Reihe von Gründen indiziert werden, einschließlich des Vorhandenseins von Bildern, nicht unterstützten Dateitypen oder beim Indizieren von Dateigrößenbeschränkungen.</span><span class="sxs-lookup"><span data-stu-id="a9ed6-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="a9ed6-107">Weitere Informationen zur Verarbeitung von Unterstützung und teilweise indizierten Elementen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="a9ed6-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="a9ed6-108">Unterstützte Dateitypen in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a9ed6-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="a9ed6-109">Teilweise indizierte Elemente in der Inhaltssuche in Office 365</span><span class="sxs-lookup"><span data-stu-id="a9ed6-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="a9ed6-110">Von der Exchange-Suche indizierte Dateiformate</span><span class="sxs-lookup"><span data-stu-id="a9ed6-110">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="a9ed6-111">Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="a9ed6-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="a9ed6-112">Anzeigen erweiterter Indizierungs Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="a9ed6-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="a9ed6-113">Nachdem der erweiterte Indizierungsprozess abgeschlossen ist, können Sie ein Verständnis der Effektivität der erneuten Verarbeitung erhalten.</span><span class="sxs-lookup"><span data-stu-id="a9ed6-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="a9ed6-114">In der Ansicht Erweiterte Indizierungs Ergebnisse auf der Registerkarte **Verarbeitung** für einen Fall wird im Diagramm die Anzahl der Elemente aufgeführt, die dem *Hybrid Index*hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a9ed6-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="a9ed6-115">Der Hybrid Index ist der Ort, an dem Advanced eDiscovery die wiederaufgearbeiteten Inhalte speichert.</span><span class="sxs-lookup"><span data-stu-id="a9ed6-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="a9ed6-116">Diese Ansicht enthält auch die Anzahl der Elemente, die eine Korrektur erfordern, und ein weiteres Diagramm mit Fehlern nach Dateityp.</span><span class="sxs-lookup"><span data-stu-id="a9ed6-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="a9ed6-117">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="a9ed6-117">For more information, see:</span></span>

- [<span data-ttu-id="a9ed6-118">Beheben von Fehlern beim Verarbeiten von Daten</span><span class="sxs-lookup"><span data-stu-id="a9ed6-118">Error remediation when processing data</span></span>](error-remediation.md)

- [<span data-ttu-id="a9ed6-119">Korrektur von Fehlern einzelner Elemente</span><span class="sxs-lookup"><span data-stu-id="a9ed6-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="a9ed6-120">Aktualisieren des erweiterten Index für depotverwalter</span><span class="sxs-lookup"><span data-stu-id="a9ed6-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="a9ed6-121">Wenn eine Depotstelle einem erweiterten eDiscovery-Fall hinzugefügt wird, werden alle teilweise indizierten Elemente neu verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a9ed6-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="a9ed6-122">Im Laufe der Zeit werden dem Postfach eines Benutzers oder dem OneDrive-Konto jedoch möglicherweise mehr teilweise indizierte Elemente hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a9ed6-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="a9ed6-123">Bei Bedarf können Sie den Index für eine bestimmte Depotbank aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a9ed6-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="a9ed6-124">Weitere Informationen finden Sie unter [Manage depotbanks in a Advanced eDiscovery Case](manage-new-custodians.md#re-index-custodian-data).</span><span class="sxs-lookup"><span data-stu-id="a9ed6-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="a9ed6-125">Sie können den Index für alle Verwalter in einem Fall auch aktualisieren, indem Sie auf der Registerkarte **Verarbeitung** auf den **Index aktualisieren** klicken.</span><span class="sxs-lookup"><span data-stu-id="a9ed6-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="a9ed6-126">Das Aktualisieren von Depot Indizes ist ein langwieriger Prozess.</span><span class="sxs-lookup"><span data-stu-id="a9ed6-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="a9ed6-127">Es wird empfohlen, dass Sie Indizes nicht mehr als einmal pro Tag in einem Fall aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a9ed6-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>
