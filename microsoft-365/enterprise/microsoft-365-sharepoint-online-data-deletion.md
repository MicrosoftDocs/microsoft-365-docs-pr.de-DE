---
title: Microsoft 365 SharePoint Online Datenlöschung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: Erfahren Sie, wie das Löschen von Daten in SharePoint Online funktioniert, beispielsweise wo gelöschte Inhalte gespeichert werden und wie lange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5cea1b797d078f6ae627700b28c6fb90cc005637
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690717"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a><span data-ttu-id="1cd72-103">SharePoint Online Löschen von Daten in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1cd72-103">SharePoint Online Data Deletion in Microsoft 365</span></span>

<span data-ttu-id="1cd72-104">SharePoint Online speichert Objekte als abstrahierten Code in Anwendungsdatenbanken.</span><span class="sxs-lookup"><span data-stu-id="1cd72-104">SharePoint Online stores objects as abstracted code within application databases.</span></span> <span data-ttu-id="1cd72-105">Wenn ein Benutzer eine Datei in SharePoint Online hochlädt, wird diese Datei zerlegt und in Anwendungscode übersetzt und in mehreren Tabellen in mehreren Datenbanken gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1cd72-105">When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases.</span></span> <span data-ttu-id="1cd72-106">In SharePoint Online werden alle Inhalte, die ein Kunde hoch lädt, in Segmente unterteilt, verschlüsselt (potenziell mit mehreren AES 256-Bit-Schlüsseln) und über das Rechenzentrum verteilt.</span><span class="sxs-lookup"><span data-stu-id="1cd72-106">In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter.</span></span> <span data-ttu-id="1cd72-107">Spezifische Details zum Segmentierungs-und Verschlüsselungsprozess finden Sie unter [Encryption in the Microsoft Cloud](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span><span class="sxs-lookup"><span data-stu-id="1cd72-107">For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span></span> 

<span data-ttu-id="1cd72-108">In SharePoint Online werden Elemente für 93 Tage ab dem Zeitpunkt aufbewahrt, zu dem Sie Sie aus Ihrem ursprünglichen Speicherort löschen.</span><span class="sxs-lookup"><span data-stu-id="1cd72-108">In SharePoint Online, items are retained for 93 days from the time you delete them from their original location.</span></span> <span data-ttu-id="1cd72-109">Sie bleiben die gesamte Zeit im Papierkorb der Website, es sei denn, jemand löscht sie von dort oder entleert diesen Papierkorb.</span><span class="sxs-lookup"><span data-stu-id="1cd72-109">They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin.</span></span> <span data-ttu-id="1cd72-110">In diesem Fall wechseln die Elemente in den Papierkorb der Websitesammlung, wo Sie für die restlichen 93 Tage bleiben.</span><span class="sxs-lookup"><span data-stu-id="1cd72-110">In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days.</span></span> <span data-ttu-id="1cd72-111">Informationen zum Wiederherstellen gelöschter Elemente finden Sie unter [Wiederherstellen von Elementen im Papierkorb einer SharePoint-Website](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) und [Wiederherstellen gelöschter Elemente aus dem Papierkorb der Websitesammlung](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b).</span><span class="sxs-lookup"><span data-stu-id="1cd72-111">For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b).</span></span> <span data-ttu-id="1cd72-112">Die Aufbewahrungszeit für den Papierkorb kann nicht in SharePoint Online konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1cd72-112">The Recycle Bin retention time is not configurable in SharePoint Online.</span></span>

<span data-ttu-id="1cd72-113">Wenn Sie eine Websitesammlung löschen, löschen Sie auch die Hierarchie der Websites in der Auflistung und alle darin enthaltenen Inhalte:</span><span class="sxs-lookup"><span data-stu-id="1cd72-113">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, and all content within them:</span></span>

- <span data-ttu-id="1cd72-114">Dokumente und Dokumentbibliotheken</span><span class="sxs-lookup"><span data-stu-id="1cd72-114">Documents and document libraries</span></span>
- <span data-ttu-id="1cd72-115">Listen und Listendaten</span><span class="sxs-lookup"><span data-stu-id="1cd72-115">Lists and list data</span></span>
- <span data-ttu-id="1cd72-116">Website Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="1cd72-116">Site configuration settings</span></span>
- <span data-ttu-id="1cd72-117">Rollen-und Sicherheitsinformationen im Zusammenhang mit der Website oder ihren Unterwebsites</span><span class="sxs-lookup"><span data-stu-id="1cd72-117">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="1cd72-118">Unterwebsites der Website auf oberster Ebene, deren Inhalte und Benutzerinformationen</span><span class="sxs-lookup"><span data-stu-id="1cd72-118">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="1cd72-119">Wenn Sie versehentlich eine Websitesammlung löschen, kann Sie von einem globalen oder SharePoint-Administrator mithilfe des SharePoint admin Centers wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1cd72-119">If you accidentally delete a site collection, it can be restored by a global or SharePoint admin using the SharePoint admin center.</span></span>

<span data-ttu-id="1cd72-120">Gelöschte Websitesammlungen werden für 93 Tage aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="1cd72-120">Deleted site collections are retained for 93 days.</span></span> <span data-ttu-id="1cd72-121">Nach 93 Tagen werden Websites sowie alle Inhalte und Einstellungen, einschließlich Listen, Bibliotheken, Seiten und Unterwebsites, dauerhaft gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1cd72-121">After 93 days, sites and all their content and settings are permanently deleted, including lists, libraries, pages, and any subsites.</span></span>

<span data-ttu-id="1cd72-122">Das Löschen von Festplatten erfolgt, wenn ein Benutzer gelöschte Elemente aus dem Papierkorb der Websitesammlung löscht, wenn die Aufbewahrungs-und Sicherungs Zeiträume ablaufen oder wenn ein Administrator eine Websitesammlung mit dem [Cmdlet Remove-SPODeletedSite](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps)dauerhaft löscht.</span><span class="sxs-lookup"><span data-stu-id="1cd72-122">Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span></span> <span data-ttu-id="1cd72-123">Wenn ein Benutzer Inhalt aus SharePoint Online löscht (dauerhaft löscht oder löscht), werden auch alle Verschlüsselungsschlüssel für die gelöschten Chunks gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1cd72-123">When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted.</span></span> <span data-ttu-id="1cd72-124">Die Blöcke auf den Datenträgern, die zuvor die gelöschten Segmente gespeichert haben, werden als nicht verwendet gekennzeichnet und können wieder verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1cd72-124">The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
