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
description: ''
ms.openlocfilehash: 5ab54e84de7434a16bdf7eb7d04fad7b9af05440
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600632"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="81bee-102">Erweiterte Indizierung der Daten von Verwaltungsberechtigten</span><span class="sxs-lookup"><span data-stu-id="81bee-102">Advanced indexing of custodian data</span></span>

<span data-ttu-id="81bee-103">Wenn eine Depotbank einem erweiterten eDiscovery-Fall hinzugefügt wird, werden alle Inhalte in Office 365, die als teilweise indiziert betrachtet wurden, erneut verarbeitet, damit Sie vollständig durchsuchbar sind.</span><span class="sxs-lookup"><span data-stu-id="81bee-103">When a custodian is added to an Advanced eDiscovery case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span>  <span data-ttu-id="81bee-104">Dieser Vorgang wird als *Erweiterte Indizierung*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="81bee-104">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="81bee-105">Inhalt kann teilweise aus einer Reihe von Gründen indiziert werden, einschließlich des Vorhandenseins von Bildern, nicht unterstützten Dateitypen oder beim Indizieren von Dateigrößenbeschränkungen.</span><span class="sxs-lookup"><span data-stu-id="81bee-105">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="81bee-106">Weitere Informationen zur Verarbeitungsunterstützung in Office 365 und teilweise indizierten Elementen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="81bee-106">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="81bee-107">Unterstützte Dateitypen in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="81bee-107">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)
- [<span data-ttu-id="81bee-108">Teilweise indizierte Elemente in der Inhaltssuche in Office 365</span><span class="sxs-lookup"><span data-stu-id="81bee-108">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
- [<span data-ttu-id="81bee-109">Von der Exchange-Suche indizierte Dateiformate</span><span class="sxs-lookup"><span data-stu-id="81bee-109">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [<span data-ttu-id="81bee-110">Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="81bee-110">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="81bee-111">Anzeigen erweiterter Indizierungs Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="81bee-111">Viewing Advanced indexing results</span></span>

<span data-ttu-id="81bee-112">Nachdem der erweiterte Indizierungsprozess abgeschlossen ist, können Sie ein Verständnis der Effektivität der erneuten Verarbeitung erhalten.</span><span class="sxs-lookup"><span data-stu-id="81bee-112">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="81bee-113">In der Ansicht Depot Indizierung werden im Diagramm alle Elemente aufgeführt, die dem *Hybrid Index*hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="81bee-113">In the Custodian Indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="81bee-114">Der Hybrid Index ist der Ort, an dem Advanced eDiscovery den erneut verarbeiteten Inhalt speichert.</span><span class="sxs-lookup"><span data-stu-id="81bee-114">The hybrid index is where Advanced eDiscovery stores the re-processed content.</span></span>

<span data-ttu-id="81bee-115">Das Diagramm enthält auch die Anzahl der Elemente, die eine Korrektur erfordern, und ein weiteres Diagramm mit Fehlern nach Dateityp.</span><span class="sxs-lookup"><span data-stu-id="81bee-115">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="81bee-116">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="81bee-116">For more information, see:</span></span>

- [<span data-ttu-id="81bee-117">Beheben von Fehlern beim Verarbeiten von Daten</span><span class="sxs-lookup"><span data-stu-id="81bee-117">Error remediation when processing data</span></span>](error-remediation.md)
- [<span data-ttu-id="81bee-118">Korrektur von Fehlern einzelner Elemente</span><span class="sxs-lookup"><span data-stu-id="81bee-118">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-advanced-indexes-for-custodians"></a><span data-ttu-id="81bee-119">Aktualisieren erweiterter Indizes für depotverwalter</span><span class="sxs-lookup"><span data-stu-id="81bee-119">Updating Advanced indexes for custodians</span></span>

<span data-ttu-id="81bee-120">Wenn eine Depotstelle einem erweiterten eDiscovery-Fall hinzugefügt wird, werden alle teilweise indizierten Elemente erneut verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="81bee-120">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are re-processed.</span></span> <span data-ttu-id="81bee-121">Im Laufe der Zeit werden dem Postfach eines Benutzers oder dem OneDrive-Konto jedoch möglicherweise mehr teilweise indizierte Elemente hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="81bee-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="81bee-122">Bei Bedarf können Sie die Indizes aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="81bee-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="81bee-123">Das Aktualisieren von Depot Indizes ist ein langwieriger Prozess.</span><span class="sxs-lookup"><span data-stu-id="81bee-123">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="81bee-124">Es wird empfohlen, die Indizes in einem Fall nicht mehr als einmal pro Tag zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="81bee-124">It's recommended that you don't update indexes more than once per day in a case.</span></span>
