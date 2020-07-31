---
title: Erweiterte Indizierung von Daten für eine Untersuchung
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
description: In diesem Artikel erfahren Sie, wie Sie die erweiterte Indizierung verwenden, um sicherzustellen, dass alle Daten, die Sie untersuchen möchten, erfasst werden.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6e72ec4a41d5b32ef3837e52f21836207c6f66e1
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527577"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a><span data-ttu-id="7ecf8-103">Erweiterte Indizierung von Daten für eine Untersuchung</span><span class="sxs-lookup"><span data-stu-id="7ecf8-103">Advanced indexing of data for an investigation</span></span>

<span data-ttu-id="7ecf8-104">Inhalte im Live-System können teilweise aus einer Reihe von Gründen indiziert werden, einschließlich des Vorhandenseins von Bildern, nicht unterstützten Dateitypen oder wenn die Größenbeschränkungen für die Indizierungs Datei auftreten.</span><span class="sxs-lookup"><span data-stu-id="7ecf8-104">Content in the live system can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span> <span data-ttu-id="7ecf8-105">Wenn Sie mit Datenüberlauf mit hohem Risiko zu tun haben, möchten Sie sicherstellen, dass die Suche alle Daten erfasst, die Sie untersuchen möchten.</span><span class="sxs-lookup"><span data-stu-id="7ecf8-105">When you are dealing with high risk data spill, you want to make sure that your search captured all data that you want to investigate.</span></span> <span data-ttu-id="7ecf8-106">Wenn eine Person von Interesse zu einer Datenermittlung hinzugefügt wird, werden alle Inhalte, die als teilweise indiziert betrachtet wurden, erneut verarbeitet, damit Sie vollständig durchsuchbar sind.</span><span class="sxs-lookup"><span data-stu-id="7ecf8-106">When a person of interest is added to a Data investigation, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span> <span data-ttu-id="7ecf8-107">Dieser Vorgang wird als *Erweiterte Indizierung*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7ecf8-107">This process is called *Advanced indexing*.</span></span> 

<span data-ttu-id="7ecf8-108">Weitere Informationen zur Verarbeitung von Unterstützung und teilweise indizierten Elementen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="7ecf8-108">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="7ecf8-109">Unterstützte Dateitypen in Daten Ermittlungen</span><span class="sxs-lookup"><span data-stu-id="7ecf8-109">Supported file types in Data Investigations</span></span>](supported-filetypes-datainvestigations.md)

- [<span data-ttu-id="7ecf8-110">Teilweise indizierte Elemente in der Inhaltssuche in Office 365</span><span class="sxs-lookup"><span data-stu-id="7ecf8-110">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="7ecf8-111">Von der Exchange-Suche indizierte Dateiformate</span><span class="sxs-lookup"><span data-stu-id="7ecf8-111">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="7ecf8-112">Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="7ecf8-112">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="7ecf8-113">Anzeigen erweiterter Indizierungs Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="7ecf8-113">Viewing Advanced indexing results</span></span>

<span data-ttu-id="7ecf8-114">Nachdem der erweiterte Indizierungsprozess abgeschlossen ist, können Sie ein Verständnis der Effektivität der erneuten Verarbeitung erhalten.</span><span class="sxs-lookup"><span data-stu-id="7ecf8-114">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="7ecf8-115">In der Ansicht Personen von Interesse indiziert das Diagramm alle Elemente, die dem *Hybrid Index*hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7ecf8-115">In the People of interest indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="7ecf8-116">Im Hybrid Index werden durch Daten Untersuchungen (Preview) die wiederaufgearbeiteten Inhalte gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7ecf8-116">The hybrid index is where Data Investigations (Preview) stores the reprocessed content.</span></span>

<span data-ttu-id="7ecf8-117">Das Diagramm enthält auch die Anzahl der Elemente, die eine Korrektur erfordern, und ein weiteres Diagramm mit Fehlern nach Dateityp.</span><span class="sxs-lookup"><span data-stu-id="7ecf8-117">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="7ecf8-118">Weitere Informationen finden Sie unter [Fehlerkorrektur bei der Verarbeitung von Daten](error-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="7ecf8-118">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-people-of-interest"></a><span data-ttu-id="7ecf8-119">Aktualisieren erweiterter Indizes für interessante Personen</span><span class="sxs-lookup"><span data-stu-id="7ecf8-119">Updating Advanced indexes for people of interest</span></span>

<span data-ttu-id="7ecf8-120">Wenn eine Person von Interesse zu einer Daten Untersuchung hinzugefügt wird, werden alle teilweise indizierten Elemente erneut verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="7ecf8-120">When a person of interest is added to a data investigation, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="7ecf8-121">Im Laufe der Zeit werden dem Postfach eines Benutzers oder dem OneDrive-Konto jedoch möglicherweise mehr teilweise indizierte Elemente hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7ecf8-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="7ecf8-122">Bei Bedarf können Sie die Indizes aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7ecf8-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="7ecf8-123">Das Aktualisieren von Indizes für Personen mit Interesse ist ein langwieriger Prozess.</span><span class="sxs-lookup"><span data-stu-id="7ecf8-123">Updating people of interest indexes is a long running process.</span></span> <span data-ttu-id="7ecf8-124">Es wird empfohlen, dass Sie Indizes nicht mehr als einmal pro Tag in einer Untersuchung aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7ecf8-124">It's recommended that you don't update indexes more than once per day in an investigation.</span></span>
